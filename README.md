# bootstrap-datepicker

Simple date/time picker component based on the work of Stefan Petre  [original code](http://www.eyecon.ro/bootstrap-datepicker/); with contributions taken from Andrew Rowls and jdewit.

# Options

These are the default options for initializing the widget:

*  `autoClose: false,          `// closes the datetimepicker
*  `maskInput: true,`           // disables the text input mask
*  `pickDate: true,`            // disables the date picker
*  `pickTime: true,`            // disables de time picker
*  `pick12HourFormat: false,`   // enables the 12-hour format time picker
*  `pickSeconds: true,`         // disables seconds in the time picker
*  `startDate: -Infinity,`      // set a minimum date
*  `endDate: Infinity`          // set a maximum date
*  `collapse: true,`
*  `calendarWeeks: false,`
*  `todayBtn: false,`
*  `doneBtn: false,`
  

# API

The widget class provides 4 methods to manipulate dates: ‘getDate’/’setDate’ for working with UTC and ‘getLocalDate’/’setLocalDate’ for working with local dates:

<pre><code>// Considering you are on a GMT-3 timezone and the input contains '2000-01-17 10:00'
var localDate = picker.getLocalDate(); // localDate === 2000-01-17 07:00
var utcDate = picker.getDate(); // utcDate === 2000-01-17 10:00
//
picker.setLocalDate(new Date(1998, 10, 11, 4, 30)); // input === 1998-10-11 07:30
picker.setDate(new Date(Date.UTC(1998, 10, 11, 4, 30))); // input === 1998-10-11 04:30</code></pre>

The date value can be unset by passing ‘null’ to any of the ‘set’ methods or by erasing the input:
<pre><code>
var picker = $('#datetimepicker').data('datetimepicker');
picker.setLocalDate(null);
// or
picker.setDate(null);
// or
input.val('');
input.change();</pre></code>
The only event exposed is ‘changeDate’, which will expose ‘date’ and ‘localDate’ properties on the event object:
<pre><code>
el.on('changeDate', function(e) {
  console.log(e.date.toString());
  console.log(e.localDate.toString());
});</pre></code>

  
# Complete sample markup



Copy and paste the following code in a file(eg: test.html) and it should produce a widget similar to the first demo:
```
<!DOCTYPE HTML>
<html>
  <head>
    <link href="http://netdna.bootstrapcdn.com/bootstrap/3.0.3/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" type="text/css" media="screen"
     href="https://raw.github.com/sahotaparamjitsingh/bootstrap-datetimepicker/master/build/css/bootstrap-datetimepicker.min.css">
  </head>
  <body>
  <div class="well">
  	<div id="datetimepicker" class="input-group date">
  	  <input type="text" class="form-control">
  	  <span class="input-group-addon"><span class="glyphicon glyphicon-calendar"></span></span>
  	</div>
  </div>
    <script type="text/javascript"
     src="http://cdnjs.cloudflare.com/ajax/libs/jquery/2.0.3/jquery.min.js">
    </script> 
    <script type="text/javascript"
     src="http://netdna.bootstrapcdn.com/bootstrap/3.0.3/js/bootstrap.min.js">
    </script>
    <script type="text/javascript"
     src="https://github.com/sahotaparamjitsingh/bootstrap-datetimepicker/blob/master/src/js/bootstrap-datetimepicker.js">
    </script>
    <script type="text/javascript"
     src="https://raw.github.com/sahotaparamjitsingh/bootstrap-datetimepicker/master/src/js/locales/bootstrap-datetimepicker.pt-BR.js">
    </script>
    <script type="text/javascript">
      $('#datetimepicker').datetimepicker({
        format: 'dd/MM/yyyy hh:mm:ss',
        language: 'pt-BR'
      });
    </script>
  </body>
<html>
```
