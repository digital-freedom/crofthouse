---
title: calendars
---
### Our availability calendar
<button class="button calendar" onclick="prev()"><< Earlier</button>
<button class="button calendar" onclick="next()">Later >></button>
<div class="grid">
    <div id="calendar0" class="size-1-3"></div>
    <div id="calendar1" class="size-1-3"></div>
    <div id="calendar2" class="size-1-3"></div>
</div>
<div class="grid">
<div class="">
<table style="width:150px">
<tr class="booked"><td>Confirmed Booking</td></tr>
</table>
</div>
<div class="">
<table style="width:150px">
<tr class="provisional"><td>Provisional Booking</td></tr>
</table>
</div>
<div class="">
<table style="width:150px">
<tr class="free"><td>This could be your week!</td></tr>
</table>
</div>
</div>

<script>
        $(document).ready(function() {


            var cal0 = $('#calendar0');
            var cal1 = $('#calendar1');
            var cal2 = $('#calendar2');


    cal0.fullCalendar({
        googleCalendarApiKey: 'AIzaSyBl_bxQ1_qO7M5SiIx0POw--cCgN0oNHOY',
        header: {
            left: '',
            center: '',
            right: 'title'
        },
        eventClick: function(event) {
        if (event.url) {
            return false;
            }
        },
        firstDay: 6,
        defaultDate: moment(),
        height: 320,
        Duration: '4:00:00',
        eventSources: [
        {
            googleCalendarId: 'bplfn5cof1gaaj0hm0jel29ig8@group.calendar.google.com',
            className: 'gcal-booked',
            rendering: 'background',
            color: 'red'
        },
        {
            googleCalendarId: '9aige4glqf2a18opgr8ehmtebk@group.calendar.google.com',
            className: 'gcal-prov',
            rendering: 'background',
            color: '#1BB3E9'
        },
        ],
        viewRender: function (view, element) {
            cur = view.intervalStart;
            d1 = moment(cur).add(1, 'months');
            cal1.fullCalendar('gotoDate', d1);
            d2 = moment(cur).add(2, 'months');
            cal2.fullCalendar('gotoDate', d2);

        },
    });

    cal1.fullCalendar({
        googleCalendarApiKey: 'AIzaSyBl_bxQ1_qO7M5SiIx0POw--cCgN0oNHOY',
        header: {
            left: '',
            center: '',
            right: 'title'
        },
        eventClick: function(event) {
        if (event.url) {
            return false;
            }
        },
        firstDay: 6,
        defaultDate: moment(cur).add(1, 'months'),
        height: 320,
        Duration: '12:00:00',
        eventSources: [
        {
            googleCalendarId: 'bplfn5cof1gaaj0hm0jel29ig8@group.calendar.google.com',
            className: 'gcal-booked',
            rendering: 'background',
            color: 'red'
        },
        {
            googleCalendarId: '9aige4glqf2a18opgr8ehmtebk@group.calendar.google.com',
            className: 'gcal-prov',
            rendering: 'background',
            color: '#1BB3E9'
        },
        ],
    });
    cal2.fullCalendar({
        googleCalendarApiKey: 'AIzaSyBl_bxQ1_qO7M5SiIx0POw--cCgN0oNHOY',
        header: {
            left: '',
            center: '',
            right: 'title'
        },
        firstDay: 6,
        eventClick: function(event) {
        if (event.url) {
            return false;
            }
        },
        defaultDate: moment(cur).add(2, 'months'),
        height: 320,
        Duration: '12:00:00',
        eventSources: [
        {
            googleCalendarId: 'bplfn5cof1gaaj0hm0jel29ig8@group.calendar.google.com',
            className: 'gcal-booked',
            rendering: 'background',
            color: 'red'
        },
        {
            googleCalendarId: '9aige4glqf2a18opgr8ehmtebk@group.calendar.google.com',
            className: 'gcal-prov',
            rendering: 'background',
            color: '#1BB3E9'
        },
        ],
    });


})
    </script>

<script>
function prev() {
    $('#calendar0').fullCalendar('gotoDate',moment(cur).add(-3, 'months'));
}
function next() {
    $('#calendar0').fullCalendar('gotoDate',moment(cur).add(3, 'months'));
}
</script>
