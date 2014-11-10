# react-tab-panel

> React Tab Panel

This component is a very simple yet powerful tab panel. You only have to require it (there are no css files involved).

For flexibility it leaves styling up to the end-user. (It does render html with some css class names, so you can use those to style your component).

## Install

```sh
$ npm install react-tab-panel
```

## Usage

```jsx
var React    = require('react')
var TabPanel = require('react-tab-panel')

var App = React.createClass({

    getInitialState: function(){
        return {
            activeIndex: 1
        }
    },

    handleChange: function(index){
        this.setState({
            activeIndex: index
        })
    },

    render: function() {
        return (
            <TabPanel activeIndex={this.state.activeIndex}
                onChange={this.handleChange}
                titleStyle={{padding: 10}}
            >
                <div title="One">first</div>
                <div title="Two">second</div>
                <div title="Three">third</div>
            </TabPanel>
        )
    }
})

React.render( <App />, document.body)
```

## Properties

The TabPanel supports the following props:

 * activeIndex: Number - the index of the TabPanel children to be rendered as active

 * onChange: Function(index) - the function to be called when the user selects another tab to be the active tab. The first param is the new activeIndex to be set

 * titleStyle: Object - style to be applied to tab titles
 * defaultStyle: Object - style to be applied to every tab in the tabpanel.

For tab titles, the children of the TabPanel are expected to have have either a **title** property, or a **tabTitle** property (the tabTitle property has higher priority, and will be used if specified as s truthy value).

## Styling

For styling, the following classes are present in the rendered html:

 * 'tab-panel' - className for the React component.
 * 'tab-panel-strip' - the nav element containing the tab titles
 * 'tab-panel-item-title' - a **li** with the title of each tab
 * 'tab-panel-item-title.active' - the active version of the above
 * 'tab-panel-container' - the body of the tab panel
 * 'tab-panel-item' - html **article** tags inside the .tab-panel-container. Those hold the actual children of the tab panel
 * 'tab-panel-item.active' - the active version of the above
