# Annex C: Notebook metadata

It is recommended to embed metadata information in each notebook. A Jupyter Notebook is a JSON file, which can be modified via a text editor.. Right at the end of the JSON file is a "metadata section", which can be enriched with a set of metadata keys (see table below).

The following table provides an overview of mandatory and optional metadata keys and a description thereof. Please note that the specified keys are case-sensitive.

\>> TEIG to decide which encoding to use for this: EUMETSAT, schema.org or STAC ?  Only the encoding selected should then remain in the document.

## OPTION 1: Original example from EUMETSAT


|**Metadata key**|**Description**|**Requirement level**|
| :-: | :-: | :-: |
|author|Author of the notebook|mandatory|
|title|Title of the notebook|mandatory|
|description|A short description of what the notebook is about (1-2 sentences max)|mandatory|
|image|link to the thumbnail image (to be provided in the Gitlab / Github repository) - Dimensions: 400px x 250 px|optional|
|services|Provide information about where the notebooks are published or can be executed|mandatory|
|tags|<p>tags	A dictionary with a set of additional metadata keys that help to construct the search interface:</p><p>- domain, e.g. Atmosphere, Ocean, Climate</p><p>- subtheme, e.g. Atmospheric Composition, Dust, Fire, ...</p><p>- platform</p><p>- sensor</p><p>- service </p><p>- tags (can be a list of variables e.g. Nitrogen dioxide concentration (tropospheric column)</p><p></p><p>Please note: the keys listed here are not mandatory and have to be defined if available..</p><p></p>|optional|


The example below illustrates how the above properties (up to the tags section) can be added to the “metadata” property of the notebook file. 


|<p>"metadata": {</p><p>`    `"author": "Julia Wagemann",</p><p>`    `"title": "Explore AC SAF Metop-A/B GOME-2 - Tropospheric Nitrogen Dioxide L2 - Part 1",</p><p>`    `"description": "This notebook is the first of two 'data discovery' modules on AC SAF Metop-A GOME-2 data. It shows you how AC SAF Metop-A GOME-2 Level 2 data are structured and how the variable 'Tropospheric Nitrogen Dioxide (NO2)' can be visualised.",</p><p>`    `"image": "../img/211\_img.png",</p><p>`    `"services": {</p><p>`        `"eumetsat": {</p><p>`            `"jupyter": {</p><p>`                `"link": "https://ltpy.adamplatform.eu/hub/user-redirect/lab/tree/20\_data\_exploration/211\_Metop-A\_GOME-2\_NO2Tropo\_L2\_load\_browse.ipynb",</p><p>`                `"service\_contact": "ltpy@meeo.it",</p><p>`                `"service\_provider": "MEEO s.r.l."</p><p>`            `},</p><p>`            `"git": {</p><p>`                `"link":"https://gitlab.eumetsat.int/eumetlab/atmosphere/atmosphere/-/blob/master/20\_data\_exploration/211\_Metop-A\_GOME-2\_NO2Tropo\_L2\_load\_browse.ipynb",</p><p>`                `"service\_contact": "training@eumetsat.int",</p><p>`                `"service\_provider": "EUMETSAT"</p><p>`            `},</p><p>`            `"colab": {</p><p>`                `"link":"$$$",</p><p>`                `"service\_contact": "training@eumetsat.int",</p><p>`                `"service\_provider": "EUMETSAT"</p><p>`            `},</p><p>`            `"binder": {</p><p>`                `"link":"$$$",</p><p>`                `"service\_contact": "training@eumetsat.int",</p><p>`                `"service\_provider": "EUMETSAT"</p><p>`            `}</p><p>`        `}</p><p>`    `},</p><p>`    `"tags": {</p><p>`        `"domain": "Atmosphere",</p><p>`        `"subtheme": "Air quality",</p><p>`        `"service": "AC SAF",</p><p>`        `"platform": "Metop-A",</p><p>`        `"sensor": "GOME-2",</p><p>`        `"tags": "Nitrogen dioxide (tropospheric column)"</p><p>`    `},</p>|
| :- |


## OPTION 2: schema.org encoding

The following table provides an overview of mandatory and optional metadata keys and a description thereof. The specified keys are case-sensitive.  The keys correspond to properties of a <https://schema.org/CreativeWork> object.


|**Metadata key**|**Type**|**Description**|**Requirement level**|
| :-: | :-: | :-: | :-: |
|identifier|Text|Identifier of the notebook.|optional|
|author|Person | [ Person ] |<p>Author(s) of the notebook. For example: </p><p></p><p>{<br>`   `"familyName": "Wagemann",<br>`   `"givenName": "Julia"</p><p>},</p><p></p>|mandatory|
|name|Text|<p>Title of the notebook.  For example:</p><p></p><p>"Explore AC SAF Metop-A/B GOME-2 - Tropospheric Nitrogen L2 - Part 1"</p>|mandatory|
|description|Text|<p>A short description of what the notebook is about (1-2 sentences max).  Example:</p><p></p><p>“This notebook is the first of two 'data discovery' modules on AC SAF Metop-A GOME-2 data. It shows you how AC SAF Metop-A GOME-2 Level 2 data are structured and how the variable 'Tropospheric Nitrogen Dioxide (NO2)' can be visualised.”</p><p></p>|mandatory|
|image|URL|<p>Link to the thumbnail image (to be provided in the Gitlab / Github repository) - Dimensions: 400px x 250 px.</p><p></p>|optional|
|potentialAction|[ Action ]|<p>Provide information about where the notebooks are published or can be executed.</p><p></p><p>Example 1 (GitLab):</p><p></p><p>{</p><p>`   `"name": "GitLab",</p><p>`   `"target": "https://gitlab.eumetsat.int/eumetlab/atmosphere/atmosphere/-/blob/master/20\_data\_exploration/211\_Metop-A\_GOME-2\_NO2Tropo\_L2\_load\_browse.ipynb",<br>`   `"provider": {<br>`      `"name": "EUMETSAT",<br>`      `"email": "training@eumetsat.int"<br>`   `}<br>}</p><p></p><p>Example 2 (Binder):</p><p>{</p><p>`   `"name": "Launch Binder",</p><p>`   `"target": "https://mybinder.org/v2/gh/ceos-seo/data\_cube\_notebooks/master?labpath=%2Fnotebooks%2Fwater%2Fcoastline%2FCoastline\_Classifier.ipynb"</p><p>}</p><p></p><p>Example 3 (Colab):</p><p>{</p><p>`   `"name": "Open in Google Colab",</p><p>`   `"target": "https://colab.research.google.com/github/ceos-seo/data\_cube\_notebooks/blob/master/notebooks/water/coastline/Coastline\_Classifier.ipynb"</p><p>}</p><p></p>|optional|
|keywords|[ Text | DefinedTerm ]|<p>Set of additional keywords (DefinedTerm) from GCMD controlled vocabularies to identify:</p><p>- Domain and subtheme as science keyword.</p><p>- Platform (e.g. satellite)</p><p>- Instrument</p><p></p><p>And additional free text keywords.  Each DefinedTerm may include a “name” (mandatory); “@id” (optional) and “inDefinedTermSet” (mandatory) property.</p>|mandatory|
|domain|DefinedTerm|<p>Example:</p><p></p><p>{</p><p>"name": "ATMOSPHERE",</p><p>"@id": "https://gcmd.earthdata.nasa.gov/kms/concept/c47f6052-634e-40ef-a5ac-13f69f6f4c2a",</p><p>`				`"inDefinedTermSet": "https://gcmd.earthdata.nasa.gov/kms/concepts/concept\_scheme/sciencekeywords"</p><p>}</p>||
|platform|DefinedTerm|<p>Example:</p><p></p><p>{</p><p>"name": "METOP-A",</p><p>"@id": "https://gcmd.earthdata.nasa.gov/kms/concept/8143808e-1005-4fed-a469-c2bd5f1521bf",<br>"inDefinedTermSet": "https://gcmd.earthdata.nasa.gov/kms/concepts/concept\_scheme/platforms"</p><p>}</p><p></p>||
|instrument|DefinedTerm|<p>Example:</p><p></p><p>{</p><p>"name": "GOME-2",</p><p>"@id": "https://gcmd.earthdata.nasa.gov/kms/concept/5eaf2209-904b-49c8-b99f-1e8550cf95d0",</p><p>"inDefinedTermSet": "https://gcmd.earthdata.nasa.gov/kms/concepts/concept\_scheme/instruments"</p><p>},</p><p></p>||
|tags|Text|<p>Example:</p><p></p><p>"AC SAF", "Nitrogen dioxide (tropospheric column)"</p>||
|license|URL | Text|<p>URL or SPDX identifier of the license, e.g. "<https://spdx.org/licenses/MIT>" or “MIT”</p><p></p>|optional|


The example below illustrates how the above properties (up to the keywords section) can be added to the “metadata” property of the notebook file.  The “kernelspec” and “language\_info” information is typically already present in the metadata object and the additional notebook metadata data can be added in front :


|<p>{</p><p>`	`"metadata": {</p><p>`		`"identifier": "eum\_211\_metop-a\_gome-2\_no",</p><p>`		`"author": {</p><p>`			`"familyName": "Wagemann",</p><p>`			`"givenName": "Julia"</p><p>`		`},</p><p>`		`"name": "Explore AC SAF Metop-A/B GOME-2 - Tropospheric Nitrogen L2 - Part 1",</p><p>`		`"description": "This notebook is rhe first of two 'data discovery' modules on AC SAF Metop-A GOME-2 data.",</p><p>`		`"image": "../img/211\_img.png",</p><p>`		`"license": "https://spdx.org/licenses/MIT",</p><p>`		`"potentialAction": [</p><p>`			`{</p><p>`				`"name": "GitLab",</p><p>`				`"target": "https://gitlab.eumetsat.int/eumetlab/atmosphere/atmosphere/-/blob/master/20\_data\_exploration/211\_Metop-A\_GOME-2\_NO2Tropo\_L2\_load\_browse.ipynb",</p><p>`				`"provider": {</p><p>`					`"name": "EUMETSAT",</p><p>`					`"email": "training@eumetsat.int"</p><p>`				`}</p><p>`			`},</p><p>`			`{</p><p>`				`"name": "Git",</p><p>`				`"target": "https://gitlab.eumetsat.int/eumetlab/atmosphere/-/blob-master/20\_data\_exploration/211",</p><p>`				`"provider": {</p><p>`					`"name": "EUMETSAT",</p><p>`					`"email": "training@eumetsat.int"</p><p>`				`}</p><p>`			`},</p><p>`			`{</p><p>`				`"target": "$$$",</p><p>`				`"name": "Google Colab",</p><p>`				`"provider": {</p><p>`					`"name": "EUMETSAT",</p><p>`					`"email": "training@eumetsat.int"</p><p>`				`}</p><p>`			`},</p><p>`			`{</p><p>`				`"target": "$$$",</p><p>`				`"name": "Binder",</p><p>`				`"provider": {</p><p>`					`"name": "EUMETSAT",</p><p>`					`"email": "training@eumetsat.int"</p><p>`				`}</p><p>`			`}</p><p>`		`],</p><p>`		`"keywords": [</p><p>`			`{</p><p>`				`"name": "ATMOSPHERE",</p><p>`				`"inDefinedTermSet": "https://gcmd.earthdata.nasa.gov/kms/concepts/concept\_scheme/sciencekeywords"</p><p>`			`},</p><p>`			`{</p><p>`				`"name": "AIR QUALITY",</p><p>`				`"inDefinedTermSet": "https://gcmd.earthdata.nasa.gov/kms/concepts/concept\_scheme/sciencekeywords"</p><p>`			`},</p><p>`			`{</p><p>`				`"name": "METOP-A",</p><p>`				`"inDefinedTermSet": "https://gcmd.earthdata.nasa.gov/kms/concepts/concept\_scheme/platforms"</p><p>`			`},</p><p>`			`{</p><p>`				`"name": "GOME-2",</p><p>`				`"inDefinedTermSet": "https://gcmd.earthdata.nasa.gov/kms/concepts/concept\_scheme/instruments"</p><p>`			`},</p><p>`			`"AC SAF",</p><p>`			`"Nitrogen dioxide (tropospheric column)"</p><p>`		`],</p><p>`		`"kernelspec": {</p><p>`			`"display\_name": "Python 3 (ipykernel)",</p><p>`			`"language": "python",</p><p>`			`"name": "python3"</p><p>`		`},</p><p>`		`"language\_info": {</p><p>`			`"codemirror\_mode": {</p><p>`				`"name": "ipython",</p><p>`				`"version": 3</p><p>`			`},</p><p>`			`"file\_extension": ".py",</p><p>`			`"mimetype": "text/x-python",</p><p>`			`"name": "python",</p><p>`			`"nbconvert\_exporter": "python",</p><p>`			`"pygments\_lexer": "ipython3",</p><p>`			`"version": "3.10.4"</p><p>`		`}</p><p>`	`}</p><p>}</p><p></p>|
| :- |



