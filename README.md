# mdd-webapp

Concepts behind a model-driven based web application.

## Table of contents

- [Architecture](#architecture)
  - [Back-end](#back-end)
  - [Front-end](#front-end)
- [Todo](#todo)

<div id='architecture'/>
## Architecture

<div id='back-end'/>
### Back-end

Components:

* list of models
* each **model** have a form associated to it
* a **form** enriches the fields of the model by adding more information to them
* this information includes:
  * required/not-required
  * HTML element and eventual associated information (e.g. "select", with predefined values, or date-picker, or date-range with default initital and end date)
* each model is exposed via API, in order to allow management of resources
* each form is exposed via API, in order to focus definition of models and related form on the back-end side

<div id='front-end'/>
### Front-end

#### Components

##### "Form" component - For create or update.

Methods are:
* *html()* - it returns the html for visualizing the form
* *save()* - it creates a new resource
* *update()* - it updates an existing resource 

##### "Table" component - For retrieve or delete. 

Methods are:
* *html()* - it returns the html for visualizing the table
* *retrieve()* - it returns a list of resources (using pagination)
* *delete()* - it delete one single resource

Input for both "Form" component and "Table" component are:
* Resource API endpoint - for example: "http://api.com/resource"
* Form API endpoint - for example: "http://api.com/resource/form"

#### Notes for form visualization

|Type|Html Element|
|---|---|
|String|select, input, textarea|
|Number|select, input|
|Boolean|Checkbox|
|Object| Recursively, based on: String, Number, Boolean, Object, Array|
|Array|List of <other type>|
|Date|date-picker, date-range|
|function|NA|


<div id='todo'/>
## TODO

- [X] Make first draft of the main concepts
- [ ] Make diagram of the architecture
- [ ] Choose elements for the implementation
- [ ] Add first example of implementation
- [ ] Abstract and package components
- [ ] Publish packages