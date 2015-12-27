---
layout: post
title: "Build a Modal Dialog Kentico Bizform"
excerpt: "Implement Modals as a custom WebPart in Kentico, resulting in an easy way to add modal dialog Bizforms to your site."
tags: [kentico]
comments: true
---

Modal dialogs, or popup windows, provide a means to present focused content (text, form, external content, etc.) to the user. Both [Bootstrap](http://getbootstrap.com/javascript/#modals) and [Foundation](http://foundation.zurb.com/docs/components/reveal.html) make implementing these modal dialogs extremely easy.

In this post, we are going to take this a step further by creating a custom Bizform WebPart, resulting in an easy way to add modal dialog Bizforms to your site.

---

**Note**: I'm bypassing basic usage of both [Boostrap](http://getbootstrap.com/getting-started/) and [Foundation](http://foundation.zurb.com/develop/getting-started.html). Please consult their respective documentation for *getting started* guides.

---

## Kentico Custom Bizform
For the custom Bizform, we will be:

- **Cloning** the default Bizform WebPart
- Adding the **modal markup** (*Foundation example*)
- Adding an **UpdatePanel**. *If you are displaying text on form submission, you will need this to seemlessly display your content within the modal. Otherwise, the modal will disappear, hiding your content.*

### Cloning the default Bizform Webpart
I'll be using [Kentico 8 in this example](https://docs.kentico.com/display/K8/Customizing+web+parts) (*all recent versions of Kentico have similar cloning options*). Update the *Name* and *Category* values as you please, but do make sure that *Clone webpart files* is enabled.

![screenshot of cloning bizform webpart]({{ site.url }}/images/clone-bizform-webpart.jpg)

### Adding modal markup and UpdatePanel
Once you have cloned the Bizform, open the new Bizform (.aspx) file and add the following markup around:
`<cms:BizForm ID="viewBiz" runat="server" IsLiveSite="true" />`

{% highlight html %}
<!-- Modal -->
<div id="<%= this.BizFormName %>" class="reveal-modal"
    data-reveal aria-labelledby="modalTitle"
    aria-hidden="true" role="dialog">
    <asp:UpdatePanel runat="server" ID="uxBizFormPanel" ChildrenAsTriggers="true" RenderMode="Inline">

        <!-- bizform -->
        <cms:BizForm ID="viewBiz" runat="server" IsLiveSite="true" />

        <a class="close-reveal-modal">&#215;</a>
    </asp:UpdatePanel>
</div>
{% endhighlight %}

We have now added the modal markup and UpdatePanel.

**Note** that we have also added `<%= this.BizFormName %>` to the *ID* attribute to get the selected BizForm Codename. We will use this *modal ID* value in our *modal trigger*

---

## Implement Your Kentico Custom Modal Dialog Bizform
**Scenario**: Add your *Request a Demo* Bizform to your template

- Bizform name: **Request a Demo**
- Bizform Codename: **RequestADemo**

On your template (*Design Tab*), add your new custom Bizform and select the **Request a Demo** Bizform. Once this form is added onto your page, the *modal container* will have an ID of **RequestADemo**:

{% highlight html %}
<div id="RequestADemo" class="reveal-modal"
    data-reveal aria-labelledby="modalTitle"
    aria-hidden="true" role="dialog">
{% endhighlight %}

To get this working, we now need to add the *modal trigger* to the template. In this case, we will add the markup below to the *Content Before* section of our new custom Bizform:

{% highlight html %}
<a href="#" data-reveal-id="RequestADemo">Launch modal</a>
{% endhighlight %}

The modal trigger added has its *'data-reveal-id'* value set to the Bizform Codename, effectively mapping to our *modal*. Save the Bizform Webpart, navigate to a page using your template. You should now be able to trigger the modal dialog when you click the *Launch modal* link.

Additionally, you can create a Widget based on your custom Bizform Webpart to add this functionality on a page by page basis.
