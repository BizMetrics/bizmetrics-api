---
title: Important Notes
anchor: importantnotes
---

# Important notes

Please read the following notes before using the API:

## Time fields

All of the time related fields, e.g. `*Instant`, `extCreationInstant`, etc. represent internal [Joda Time objects](http://www.joda.org/joda-time/) and they are serialized/desererialized using [jackson-datatype-joda](https://github.com/FasterXML/jackson-datatype-joda).

Most of those time fields support **different alternative formats** of representation. In some of the examples we show two different ways to represent the *Instant types (either with a String or a Number). More detailed information about the different types used internally and accepted can be found below:

<table class="table table-striped table-bordered">
	<thead>
		<tr>
			<th>Field name(s)</th>
			<th>Internal representation</th>
			<th>Format(s) details</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>
				<code>extCreationInstant</code><br/>
				<code>extLastModifiedInstant</code><br/>
				<code>extActivationDate</code><br/>
				<code>extEndDate</code><br/>
				<code>dateOfChange</code><br/>
			</td>
			<td>Joda <a href="http://joda-time.sourceforge.net/apidocs/org/joda/time/DateTime.html" target="_blank">DateTime</a></td>
			<td> a
				<a href="http://joda-time.sourceforge.net/api-release/org/joda/time/DateTime.html#parse(java.lang.String)" target="_blank"<code>String</code> type </a>
				or
				<code>Number</code> UTC milliseconds since <code>1970-01-01T00:00:00Z</code>
			</td>
		</tr>
		<tr>
			<td>
				<code>planInterval</code><br/>
				<code>subsInterval</code><br/>
			</td>
			<td>Joda <a href="http://joda-time.sourceforge.net/apidocs/org/joda/time/Period.html" target="_blank">Period</a></td>
			<td> a
				<a href="http://joda-time.sourceforge.net/apidocs/org/joda/time/format/ISOPeriodFormat.html#standard()" target="_blank"<code>String</code> type </a> with the Period represented by the ISO8601 format (see link)
				or <br/>
				A <code>Number</code> of UTC milliseconds that the period will comprise <strong>Note, this version's usage is discouraged, it's preferable to use the String type</strong> 
			</td>
		</tr>
	</tbody>
</table>


## Headers

For all of the API's methods, the usage of the Header: `Content-type: application/json` is mandatory. Without that Header, the server will not recognise the request's body as JSON.