# UI Automation Notes

## GUI Inspection Tools

- UISpy - (old and depreciated)
- Inspect - (supported and found in Microsoft SDK)
- VisualUIAVerify - (supported and found in Microsoft SDK)
- FlaUIInspect - (open source application)


## UI Automation Providers

- supply property values for each element.
- providers for a control support navigation among the controls child elements but, are not concerned with navigation between these control sub-trees.

    that is left up to the UI Automation core, using info from the default window providers.


## Client Applications

UI Automation exposes every piece of the UI to client applications as an automation element.


## UI Automation Tree

The UI Automation Tree represents the entire UI.

Tree Structure:

    Root element
        Child elements
            Child elements
                Child elements


Tree Elements:

    Desktop
        Application_Windows
            Menus, Buttons, Toolbars etc...
                List Items etc...


The order of the siblings in the UI Automation tree is quite important.
Objects next to each other visually should be next to each other in the tree.

Clients can process tree infomation more effectively by having three alternative views to use:

- Raw View              (the full tree of automation elements)
- Control View          (a subset of the raw view)
- Content View          (a subset of the control view)



## UI Automation Elements

Automation elements expose common properties of the UI elements they represent.

common properties:

- control type              (its basic appearance and functionality 

e.g:

- button
- check box
- etc...


## UI Automation Control Patterns

the current UI Automation implementation defines 22 control pattern properties.

control pattern properties describe functional aspects of automation elements.

one automation element can have multiple control pattern properties.

the __Invoke Control Pattern__ pattern is how a button describes __Click Action__ functionality.

- Annotation
- Dock
- Drag
- DropTarget
- ExpandCollapse
- Grid
- GridItem
- Invoke
- ItemContainer
- LegacyIAccessible
- MultipleView
- ObjectModel
- RangeValue
- Scroll
- ScrollItem
- Selection
- SelectionItem
- Spreadsheet
- SpreadsheetItem
- Styles
- SynchronizedInput
- Table
- TableItem
- Text
- TextChild
- TextRange
- Toggle
- Transform
- Value
- VirtualizedItem
- Window


## UI Automation Control Types

the current UI Automation implementation defines 38 control type properties.

control type properties specify well-known controls that the element represents.

- AppBar
- Button
- Calendar
- CheckBox
- ComboBox
- DataGrid
- DataItem
- Document
- Edit
- Group
- Header
- HeaderItem
- Hyperlink
- Image
- List
- ListItem
- Menu
- MenuBar
- MenuItem
- Pane
- ProgressBar
- RadioButton
- ScrollBar
- SemanticZoom
- Separator
- Slider
- Spinner
- SplitButton
- StatusBar
- Tab
- TabItem
- Table
- Text
- Thumb
- TitleBar
- ToolBar
- ToolTip
- Tree
- TreeItem
- Window

certain conditions must be meet before you can assign control types to elements.

e.g: particular

- tree structure
- property values
- control patterns
- events

You can extend a control with predefined patterns and properties, as well as custom ones.


## UI Automation Events

events notify applications of changes to, and actions taken with automation elements.

the UI Automation event model is independent of the WinEvent framework in Windows.

provider applications can choose to raise events selectively (depending on whether any clients are subscribed to those events), or choose to not raise events at all.

event category types:

- Property change
- Element action
- Structure change
- Global desktop change
- Notification

The following events may be raised even when the state of the UI has not changed:

- UIA_AutomationPropertyChangedEventId
- UIA_SelectionItem_ElementSelectedEventId
- UIA_Selection_InvalidatedEventId
- UIA_Text_TextChangedEventId

