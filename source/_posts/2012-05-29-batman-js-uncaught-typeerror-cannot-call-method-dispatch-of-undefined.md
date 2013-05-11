---
title: 'batman.js - Uncaught TypeError: Cannot call method "dispatch" of undefined'
author: admin
layout: post
permalink: /2012/05/29/batman-js-uncaught-typeerror-cannot-call-method-dispatch-of-undefined/
categories:
  - Javascript
---

> I ran in to this error:  
>   
> Uncaught TypeError: Cannot call method ‘dispatch’ of undefined  
>  


The first thing to check is that your route exists. 
I created a utility located here: [https://github.com/RyanonRails/batman.utilitybelt][1] that can list out your current routes.

 [1]: https://github.com/RyanonRails/batman.utilitybelt "https://github.com/RyanonRails/batman.utilitybelt"

If the route exists, you need to make sure that your controller names are named correctly as such:
{% codeblock lang:coffeescript %}
@resources 'sections', 'sectionrows'

-------------This would looks for these 2 controllers------------
class EST.SectionsController extends Batman.Controller
class EST.SectionrowsController extends Batman.Controller
{% endcodeblock %}
I ran into this because of the above 2 word model. For future reference here’s the layout I used:

Driver (/est.coffee):
{% codeblock lang:coffeescript %}
window.EST = class EST extends Batman.App
  Batman.ViewStore.prefix = 'app/views'
  @controller 'sectionrows'
  @model 'sectionrow'

  @resources 'sectionrows'
{% endcodeblock %}
Controller (/controllers/sectionrows_controller.coffee):
{% codeblock lang:coffeescript %}
class EST.SectionrowsController extends Batman.Controller
  routingKey: 'sectionrows'

  index: ->
    EST.SectionRow.load (err,results) =>
      @set 'sectionrows', results
{% endcodeblock %}
Model (/models/sectionrow.coffee):
{% codeblock lang:coffeescript %}
class EST.SectionRow extends Batman.Model
  @resourceName: 'sectionrow'
  @url = "/api/sectionrows"

  @set 'primaryKey', 'SectionRowId'
  @persist Batman.RestStorage
  @encode 'SectionRowId', 'WorkType'
{% endcodeblock %}
View (/views/sectionrows/index.html):
{% codeblock lang:html %}

<h2>All Section rows</h2>
 
  <div data-foreach-section="sectionrows" data-mixin="animation">
    <a data-bind="sectionrow.SectionRowId" ></a>
    <p data-bind="sectionrow.WorkType"></p>
  </div>
 
Total # of sections: <span data-bind="sectionrows.length"></span>
{% endcodeblock %}
Batman 0.9