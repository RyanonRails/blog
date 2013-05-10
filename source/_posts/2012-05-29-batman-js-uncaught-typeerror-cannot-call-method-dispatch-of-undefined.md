---
title: 'batman.js - Uncaught TypeError: Cannot call method "dispatch" of undefined'
author: admin
layout: post
permalink: /2012/05/29/batman-js-uncaught-typeerror-cannot-call-method-dispatch-of-undefined/
categories:
  - Javascript
---
# 

> I ran in to this error:  
>   
> Uncaught TypeError: Cannot call method ‘dispatch’ of undefined  
>  

The first thing to check is that your route exists. I created a utility located here: [https://github.com/RyanonRails/batman.utilitybelt][1] that can list out your current routes.

 [1]: https://github.com/RyanonRails/batman.utilitybelt "https://github.com/RyanonRails/batman.utilitybelt"

If the route exists, you need to make sure that your controller names are named correctly as such:

    @resources 'sections', 'sectionrows'
    
    -------------This would looks for these 2 controllers------------
    class EST.SectionsController extends Batman.Controller
    class EST.SectionrowsController extends Batman.Controller

I ran into this because of the above 2 word model. For future reference here’s the layout I used:

Driver (/est.coffee):

    window.EST = class EST extends Batman.App
      Batman.ViewStore.prefix = 'app/views'
      @controller 'sectionrows'
      @model 'sectionrow'
    
      @resources 'sectionrows'

Controller (/controllers/sectionrows_controller.coffee):

    class EST.SectionrowsController extends Batman.Controller
      routingKey: 'sectionrows'
    
      index: ->
        EST.SectionRow.load (err,results) =>
          @set 'sectionrows', results

Model (/models/sectionrow.coffee):

    class EST.SectionRow extends Batman.Model
      @resourceName: 'sectionrow'
      @url = "/api/sectionrows"
    
      @set 'primaryKey', 'SectionRowId'
      @persist Batman.RestStorage
      @encode 'SectionRowId', 'WorkType'

View (/views/sectionrows/index.html):

    All Section rows
    
      
        
        
      
    
    Total # of sections: 

Batman 0.9