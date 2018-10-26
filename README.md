[![Bootstrap 4.1.3](https://img.shields.io/badge/bootstrap-4.1.3-green.svg?style=flat-square)](https://getbootstrap.com/docs/4.1)  [![MIT License](https://badges.frapsoft.com/os/mit/mit.svg?style=flat-square)](https://opensource.org/licenses/mit-license.php)  

# Bootstrap 4 Toggle

**Bootstrap 4 Toggle** is a bootstrap plugin/widget that converts checkboxes into toggles.

Visit https://gitbrent.github.io/bootstrap4-toggle/ for interactive demos.

## Installation

### Download
[Version 3.0.0](https://github.com/gitbrent/bootstrap4-toggle/archive/v3.1.0.zip) is the latest version of Bootstrap4 Toggle.

### Use CDN
```html
<link href="https://cdn.jsdelivr.net/gh/gitbrent/bootstrap4-toggle@3.1.0/css/bootstrap4-toggle.min.css" rel="stylesheet">  
<script src="https://cdn.jsdelivr.net/gh/gitbrent/bootstrap4-toggle@3.1.0/js/bootstrap4-toggle.min.js"></script>
```

### Node.js
```bash
npm install bootstrap4-toggle
```

### Yarn
```bash
yarn install
```

## Usage

### Basic example
Simply add `data-toggle="toggle"` to automatically convert checkboxes into toggles.

```html
<input id="chkToggle" type="checkbox" data-toggle="toggle">
```

### Stacked checkboxes
Refer to Bootstrap Form Controls documentation to create stacked checkboxes. Simply add `data-toggle="toggle"` to convert checkboxes into toggles.

```html
<div class="form-check form-check">
  <label>
    <input type="checkbox" data-toggle="toggle">
    Option one is enabled
  </label>
</div>
<div class="form-check form-check disabled">
  <label>
    <input type="checkbox" disabled data-toggle="toggle">
    Option two is disabled
  </label>
</div>
```

### Inline Checkboxes
Refer to Bootstrap Form Controls documentation to create inline checkboxes. Simply add `data-toggle="toggle"` to a convert checkboxes into toggles.

```html
<label class="form-check form-check-inline">
  <input type="checkbox" checked data-toggle="toggle"> First
</label>
<label class="form-check form-check-inline">
  <input type="checkbox" data-toggle="toggle"> Second
</label>
<label class="form-check form-check-inline">
  <input type="checkbox" data-toggle="toggle"> Third
</label>
```

## API

### Initialize by JavaScript
Initialize toggles with id `toggle-one` with a single line of JavaScript.

```html
<input id="toggle-one" checked type="checkbox">
<script>
  $(function() {
    $('#toggle-one').bootstrapToggle();
  })
</script>
```

### Options
* Options can be passed via data attributes or JavaScript
* For data attributes, append the option name to `data-` (ex: `data-on="Enabled"`)

```html
<input type="checkbox" data-toggle="toggle" data-on="Enabled" data-off="Disabled">
<input type="checkbox" id="toggle-two">
<script>
  $(function() {
    $('#toggle-two').bootstrapToggle({
      on: 'Enabled',
      off: 'Disabled'
    });
  })
</script>
```

Name      |Type       |Default    |Description                 |
----------|-----------|----------|----------------------------|
`on`      |string/html|"On"      |Text of the on toggle
`off`     |string/html|"Off"     |Text of the off toggle
`size`    |string     |"normal"  |Size of the toggle. Possible values are: `large`, `normal`, `small`, `mini`.
`onstyle` |string     |"primary" |Style of the on toggle. Possible values are: `primary`,`secondary`,`success`,`danger`,`warning`,`info`,`light`,`dark`
`offstyle`|string     |"light"   |Style of the off toggle. Possible values are: `primary`,`secondary`,`success`,`danger`,`warning`,`info`,`light`,`dark`
`style`   |string     |           |Appends the value to the class attribute of the toggle. This can be used to apply custom styles. Refer to Custom Styles for reference.
`width`   |integer    |*null*     |Sets the width of the toggle. if set to *null*, width will be auto-calculated.
`height`  |integer    |*null*     |Sets the height of the toggle. if set to *null*, height will be auto-calculated.

### Methods
Methods can be used to control toggles directly.

```html
<input id="toggle-demo" type="checkbox" data-toggle="toggle">
```

Method     |Example                                         |Description
-----------|------------------------------------------------|------------------------------------------
initialize | `$('#toggle-demo').bootstrapToggle()`          |Initializes the toggle plugin with options
destroy    | `$('#toggle-demo').bootstrapToggle('destroy')` |Destroys the toggle
on         | `$('#toggle-demo').bootstrapToggle('on')`      |Sets the toggle to 'On' state
off        | `$('#toggle-demo').bootstrapToggle('off')`     |Sets the toggle to 'Off' state
toggle     | `$('#toggle-demo').bootstrapToggle('toggle')`  |Toggles the state of the toggle on/off
enable     | `$('#toggle-demo').bootstrapToggle('enable')`  |Enables the toggle
disable    | `$('#toggle-demo').bootstrapToggle('disable')` |Disables the toggle

## Events

### Event Propagation
Note All events are propagated to and from input element to the toggle.

You should listen to events from the `<input type="checkbox">` directly rather than look for custom events.

```html
<input id="toggle-event" type="checkbox" data-toggle="toggle">
<div id="console-event"></div>
<script>
  $(function() {
    $('#toggle-event').change(function() {
      $('#console-event').html('Toggle: ' + $(this).prop('checked'))
    })
  })
</script>
```

### API vs Input
This also means that using the API or Input to trigger events will work both ways.

```html
<input id="toggle-trigger" type="checkbox" data-toggle="toggle">
<button class="btn btn-success" onclick="toggleApiOn()" >On by API</button>
<button class="btn btn-danger"  onclick="toggleApiOff()">Off by API</button>
<button class="btn btn-success" onclick="toggleInpOn()" >On by Input</button>
<button class="btn btn-danger"  onclick="toggleInpOff()">Off by Input</button>
<script>
  function toggleApiOn() {
    $('#toggle-trigger').bootstrapToggle('on')
  }
  function toggleApiOff() {
    $('#toggle-trigger').bootstrapToggle('off')  
  }
  function toggleInpOn() {
    $('#toggle-trigger').prop('checked', true).change()
  }
  function toggleInpOff() {
    $('#toggle-trigger').prop('checked', false).change()
  }
</script>
```

## Demos
Visit https://gitbrent.github.io/bootstrap4-toggle/ for demos.
