---
title: Publications
permalink: /docs/publications/
---

##### List of published research works which ultilize ion beams from the HUS Pelletron Accelerator.

<div class="table-2">
	<table width="100%">
		<thead>
			<tr>
				<th align="left">No.</th>
				<th align="left">Title</th>
				<th align="left">Author(s)</th>
				<th align="left">Journal</th>
				<th align="left">Vol.; Number; Page</th>
				<th align="left">Year</th>
				<th align="left">Publisher</th>
			</tr>
		</thead>
		<tbody id="results"></tbody>
	</table>
</div>

<script>
	fetch("/assets/publications_database.xml")
	.then(response => response.text())
	.then((data) => {
		let parser = new DOMParser(),
		xml = parser.parseFromString(data,"text/xml");
		var no = xml.getElementsByTagName('no');
		var title = xml.getElementsByTagName('title');
		var author = xml.getElementsByTagName('author');
		var journal = xml.getElementsByTagName('journal');
		var volumne = xml.getElementsByTagName('volumne');
		var number = xml.getElementsByTagName('number');
		var page = xml.getElementsByTagName('page');
		var year = xml.getElementsByTagName('year');
		var publisher = xml.getElementsByTagName('publisher');
		for (i = 0; i < no.length; i++) {
			no_i = no[i].childNodes[0].nodeValue;
			title_i = title[i].childNodes[0].nodeValue;
			author_i = author[i].childNodes[0].nodeValue;
			journal_i = journal[i].childNodes[0].nodeValue;
			volumne_i = volumne[i].childNodes[0].nodeValue;
			number_i = number[i].childNodes[0].nodeValue;
			page_i = page[i].childNodes[0].nodeValue;
			year_i = year[i].childNodes[0].nodeValue;
			publisher_i = publisher[i].childNodes[0].nodeValue;
			const row = `<tr>
						<td align="left">${no_i}</td>
						<td align="left">${title_i}</td>
						<td align="left">${author_i}</td>
						<td align="left">${journal_i}</td>
						<td align="left">${volumne_i}; ${number_i}; ${page_i}</td>
						<td align="left">${year_i}</td>
						<td align="left">${publisher_i}</td>
						</tr>`;
			const results = document.querySelector("#results");
			results.insertAdjacentHTML("beforeend",row);
		};
	});
</script>

