# jQuery Frontier Calendar Change Log #

Change log for plugin...

## Version 1.3.2: June 24th, 2010 ##

<li> fix to getAgendaItemByDataAttr() function.<br>
<br>
<h2>Version 1.3.1: June 23rd, 2010</h2>

<li>Crucial bug fix to the <b>deleteAgendaItemByDataAttr(calId,attrName,attrValue)</b> function.<br>
<br>
<li>New <b>reRenderAgendaItems(calId)</b> function that allows you to re-render the agenda items if they get out of alignment. Download the latest zip file and read the troubleshooting section to see when you might need to use this function.<br>
<br>
<br>

<h2>Version 1.3: June 22nd, 2010</h2>

<li> Bug fixes<br>
<br>
<li> <b>Tooltips on agenda items.</b> Use any tooltip library you want. Whatever library you choose it should probably have destroy() tooltip and/or hide() tooltip methods. See documentation on <b>applyAgendaTooltipCallback(divElm,agendaItem)</b> callback function.<br>
<br>
<img src='http://jquery-frontier-calendar.googlecode.com/files/TooltipTest.png' width='400px'>

<li> Two additional callback functions for drag events, <b>agendaDragStartCallback(eventObj,divElm,agendaItem)</b> and <b>agendaDragStopCallback(eventObj,divElm,agendaItem)</b>. These are fired when dragging starts and dragging stops on agenda items (if drag-and-drop is enabled.)<br>
<br>
<li> New <b>deleteAllAgendaItems(calId)</b> method to delete all agenda items in the calendar.<br>
<br>
<li> Updated initialization for <b>applyAgendaTooltipCallback(divElm,agendaItem)</b>, <b>agendaDragStartCallback(eventObj,divElm,agendaItem)</b>, and <b>agendaDragStopCallback(eventObj,divElm,agendaItem)</b> callbacks.<br>
<pre><code><br>
var jfcalplugin = $("#mycal").jFrontierCal({<br>
date: new Date(),<br>
dayClickCallback: myDayClickHandler,<br>
agendaClickCallback: myAgendaClickHandler,<br>
agendaDropCallback: myAgendaDropHandler,<br>
agendaMouseoverCallback: myAgendaMouseoverHandler,<br>
applyAgendaTooltipCallback: myApplyTooltip,<br>
agendaDragStartCallback : myAgendaDragStart,<br>
agendaDragStopCallback : myAgendaDragStop,<br>
dragAndDropEnabled: true<br>
}).data("plugin");<br>
</code></pre>

<li> This version (like 1.2) still requires the jquery core fix for drag-and-drop under IE. I'd like to fix this so it's not required...<br>
<br>
<br>
<h2>Version 1.2: June 17th, 2010</h2>

<li>More Bug fixes<br>
<br>
<li>
<b>CSS tweaks</b><br>
New CSS attribute for the current day.<br>
Arrows on agenda items that span weeks & months.<br>
<br>
<li>
<b>Drag-and-drop agenda items!</b><br>
This required a modification to the jQuery Core library to enable drag-and-drop to work correctly in Internet Explorer.<br>
If you don't care about IE than you can use an unmodified version of the jQuery Core library. Everything works fine in Chrome, Firefox, Opera, and Safari without the fix.<br>
There is a readme file inlcuded with this plugin, <a href='http://jquery-frontier-calendar.googlecode.com/files/README-IE-FIX.TXT'>http://jquery-frontier-calendar.googlecode.com/files/README-IE-FIX.TXT</a>,<br>
that explains what was modified. Only one line was changed so not that big of a deal....<br>
<br>
<li>
<b>The jfcalplugin.addAgendaItem() method changed slightly.</b><br>
The new method signature is jfcalplugin.addAgendaItem(calId,title,startDate,endDate,allDay,data,displayProp).<br>
The new parameter is the boolean value 'allDay' which did not exist in version 1.1. This is a flag that tells the calendar the agenda item is an all day event. If you want<br>
the same exact functionality as version 1.1 then simply pass in 'false'. If you pass in 'true' then the start time will not be displayed on the agenda item.<br>
<br>
<li>
All the getAgendaItem methods return an updated agenda object which inlcudes the allDay flag.<br>
<br>
<pre><code><br>
{<br>
agendaId: [integer],<br>
title: [string],<br>
startDate: [Date],<br>
endDate: [Date],<br>
allDay: [boolean],<br>
data: {<br>
key1: [value1],<br>
key2: [value2],<br>
etc...<br>
},<br>
displayProp: {<br>
backgroundColor: [string],<br>
foregroundColor: [string]<br>
}<br>
}<br>
</code></pre>

<li>
<b>The constructor/initialize method changed slightly.</b><br>
There is a new boolean parameter called dragAndDropEnabled which allows you to turn off drag-and-drop. This is enabled by default.<br>
<pre><code><br>
var jfcalplugin = $('selector').jFrontierCal(date,dayClickCallback,agendaClickCallback,agendaDropCallback,dragAndDropEnabled)<br>
</code></pre>

<br>
<h2>Version: 1.1: June 14th</h2>
<li>Bug fixes</li>
<li>CSS tweaks</li>
<li>Basic iCal VEVENT import support.</li>

<b>(Drag-and-drop coming soon!)</b>

<br>
<h2>Version 1.0: June 9th</h2>

<li>Initial release</li>