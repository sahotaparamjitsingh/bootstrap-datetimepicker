Forked from http://tarruda.github.com/bootstrap-datetimepicker/.

API
The widget class provides 4 methods to manipulate dates: ‘getDate’/’setDate’ for working with UTC and ‘getLocalDate’/’setLocalDate’ for working with local dates:

// Considering you are on a GMT-3 timezone and the input contains '2000-01-17 10:00'
var localDate = picker.getLocalDate(); // localDate === 2000-01-17 07:00
var utcDate = picker.getDate(); // utcDate === 2000-01-17 10:00
//
picker.setLocalDate(new Date(1998, 10, 11, 4, 30)); // input === 1998-10-11 07:30
picker.setDate(new Date(Date.UTC(1998, 10, 11, 4, 30))); // input === 1998-10-11 04:30
The date value can be unset by passing ‘null’ to any of the ‘set’ methods or by erasing the input:

var picker = $('#datetimepicker'l).data('datetimepicker');
picker.setLocalDate(null);
// or
picker.setDate(null);
// or
input.val('');
input.change();
The only event exposed is ‘changeDate’, which will expose ‘date’ and ‘localDate’ properties on the event object:

el.on('changeDate', function(e) {
  console.log(e.date.toString());
  console.log(e.localDate.toString());
});

Options

These are the default options for initializing the widget:

  autoClose: false,          // closes the datetimepicker
  maskInput: true,           // disables the text input mask
  pickDate: true,            // disables the date picker
  pickTime: true,            // disables de time picker
  pick12HourFormat: false,   // enables the 12-hour format time picker
  pickSeconds: true,         // disables seconds in the time picker
  startDate: -Infinity,      // set a minimum date
  endDate: Infinity          // set a maximum date
  collapse: true,
  calendarWeeks: false,
  todayBtn: false,
  doneBtn: false,
  
