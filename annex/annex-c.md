# Annex C: Notebook metadata

It is recommended to embed metadata information in each notebook. A Jupyter Notebook is a JSON file, which can be modified via a text editor.. Right at the end of the JSON file is a "metadata section", which can be enriched with a set of metadata keys (see table below).

The following table provides an overview of mandatory and optional metadata keys and a description thereof. Please note that the specified keys are case-sensitive.

\>> TEIG to decide which encoding to use for this: EUMETSAT, schema.org or STAC ?  Only the encoding selected should then remain in the document.

## OPTION 1: Original example from EUMETSAT


|**Metadata key**|**Description**|**Requirement level**|
| :-: | :- | :-: |
|author|Author of the notebook|mandatory|
|title|Title of the notebook|mandatory|
|description|A short description of what the notebook is about (1-2 sentences max)|mandatory|
|image|link to the thumbnail image (to be provided in the Gitlab / Github repository) - Dimensions: 400px x 250 px|optional|
|services|Provide information about where the notebooks are published or can be executed|mandatory|
|tags|<p>tags	A dictionary with a set of additional metadata keys that help to construct the search interface:</p><p>- domain, e.g. Atmosphere, Ocean, Climate</p><p>- subtheme, e.g. Atmospheric Composition, Dust, Fire, ...</p><p>- platform</p><p>- sensor</p><p>- service </p><p>- tags (can be a list of variables e.g. Nitrogen dioxide concentration (tropospheric column)</p><p></p><p>Please note: the keys listed here are not mandatory and have to be defined if available..</p><p></p>|optional|


The example below illustrates how the above properties (up to the tags section) can be added to the “metadata” property of the notebook file. 


```
"metadata": {
    "author": "Julia Wagemann",
    "title": "Explore AC SAF Metop-A/B GOME-2 - Tropospheric Nitrogen Dioxide L2 - Part 1",
    "description": "This notebook is the first of two 'data discovery' modules on AC SAF Metop-A GOME-2 data. It shows you how AC SAF Metop-A GOME-2 Level 2 data are structured and how the variable 'Tropospheric Nitrogen Dioxide (NO2)' can be visualised.",
    "image": "../img/211_img.png",
    "services": {
        "eumetsat": {
            "jupyter": {
                "link": "https://ltpy.adamplatform.eu/hub/user-redirect/lab/tree/20_data_exploration/211_Metop-A_GOME-2_NO2Tropo_L2_load_browse.ipynb",
                "service_contact": "ltpy@meeo.it",
                "service_provider": "MEEO s.r.l."
            },
            "git": {
                "link":"https://gitlab.eumetsat.int/eumetlab/atmosphere/atmosphere/-/blob/master/20_data_exploration/211_Metop-A_GOME-2_NO2Tropo_L2_load_browse.ipynb",
                "service_contact": "training@eumetsat.int",
                "service_provider": "EUMETSAT"
            },
            "colab": {
                "link":"$$$",
                "service_contact": "training@eumetsat.int",
                "service_provider": "EUMETSAT"
            },
            "binder": {
                "link":"$$$",
                "service_contact": "training@eumetsat.int",
                "service_provider": "EUMETSAT"
            }
        }
    },
    "tags": {
        "domain": "Atmosphere",
        "subtheme": "Air quality",
        "service": "AC SAF",
        "platform": "Metop-A",
        "sensor": "GOME-2",
        "tags": "Nitrogen dioxide (tropospheric column)"
    },
```

## OPTION 2: schema.org encoding

The following table provides an overview of mandatory and optional metadata keys and a description thereof. The specified keys are case-sensitive.  The keys correspond to properties of a <https://schema.org/CreativeWork> object.


|**Metadata key**|**Type**|**Description**|**Requirement level**|
| :-: | :-: | :- | :-: |
|identifier|Text|Identifier of the notebook.|optional|
|author| Person \| [ Person ] |<p>Author(s) of the notebook. For example: </p><p></p><p>{<br>`   `"familyName": "Wagemann",<br>`   `"givenName": "Julia"</p><p>},</p><p></p>|mandatory|
|name|Text|<p>Title of the notebook.  For example:</p><p></p><p>"Explore AC SAF Metop-A/B GOME-2 - Tropospheric Nitrogen L2 - Part 1"</p>|mandatory|
|description|Text|<p>A short description of what the notebook is about (1-2 sentences max).  Example:</p><p></p><p>“This notebook is the first of two 'data discovery' modules on AC SAF Metop-A GOME-2 data. It shows you how AC SAF Metop-A GOME-2 Level 2 data are structured and how the variable 'Tropospheric Nitrogen Dioxide (NO2)' can be visualised.”</p><p></p>|mandatory|
|image|URL|<p>Link to the thumbnail image (to be provided in the Gitlab / Github repository) - Dimensions: 400px x 250 px.</p><p></p>|optional|
|potentialAction|[ Action ]|<p>Provide information about where the notebooks are published or can be executed.</p><p></p><p>Example 1 (GitLab):</p><p></p><p>{</p><p>`   `"name": "GitLab",</p><p>`   `"target": "https://gitlab.eumetsat.int/eumetlab/atmosphere/atmosphere/-/blob/master/20\_data\_exploration/211\_Metop-A\_GOME-2\_NO2Tropo\_L2\_load\_browse.ipynb",<br>`   `"provider": {<br>`      `"name": "EUMETSAT",<br>`      `"email": "training@eumetsat.int"<br>`   `}<br>}</p><p></p><p>Example 2 (Binder):</p><p>{</p><p>`   `"name": "Launch Binder",</p><p>`   `"target": "https://mybinder.org/v2/gh/ceos-seo/data\_cube\_notebooks/master?labpath=%2Fnotebooks%2Fwater%2Fcoastline%2FCoastline\_Classifier.ipynb"</p><p>}</p><p></p><p>Example 3 (Colab):</p><p>{</p><p>`   `"name": "Open in Google Colab",</p><p>`   `"target": "https://colab.research.google.com/github/ceos-seo/data\_cube\_notebooks/blob/master/notebooks/water/coastline/Coastline\_Classifier.ipynb"</p><p>}</p><p></p>|optional|
|keywords| [ Text \| DefinedTerm ]|<p>Set of additional keywords (DefinedTerm) from GCMD controlled vocabularies to identify:</p><p>- Domain and subtheme as science keyword.</p><p>- Platform (e.g. satellite)</p><p>- Instrument</p><p></p><p>And additional free text keywords.  Each DefinedTerm may include a “name” (mandatory); “@id” (optional) and “inDefinedTermSet” (mandatory) property.</p>|mandatory|
|domain|DefinedTerm|<p>Example:</p><p></p><p>{</p><p>"name": "ATMOSPHERE",</p><p>"@id": "https://gcmd.earthdata.nasa.gov/kms/concept/c47f6052-634e-40ef-a5ac-13f69f6f4c2a",</p><p>`				`"inDefinedTermSet": "https://gcmd.earthdata.nasa.gov/kms/concepts/concept\_scheme/sciencekeywords"</p><p>}</p>||
|platform|DefinedTerm|<p>Example:</p><p></p><p>{</p><p>"name": "METOP-A",</p><p>"@id": "https://gcmd.earthdata.nasa.gov/kms/concept/8143808e-1005-4fed-a469-c2bd5f1521bf",<br>"inDefinedTermSet": "https://gcmd.earthdata.nasa.gov/kms/concepts/concept\_scheme/platforms"</p><p>}</p><p></p>||
|instrument|DefinedTerm|<p>Example:</p><p></p><p>{</p><p>"name": "GOME-2",</p><p>"@id": "https://gcmd.earthdata.nasa.gov/kms/concept/5eaf2209-904b-49c8-b99f-1e8550cf95d0",</p><p>"inDefinedTermSet": "https://gcmd.earthdata.nasa.gov/kms/concepts/concept\_scheme/instruments"</p><p>},</p><p></p>||
|tags|Text|<p>Example:</p><p></p><p>"AC SAF", "Nitrogen dioxide (tropospheric column)"</p>||
|license|URL \| Text|<p>URL or SPDX identifier of the license, e.g. "<https://spdx.org/licenses/MIT>" or “MIT”</p><p></p>|optional|


The example below illustrates how the above properties (up to the keywords section) can be added to the “metadata” property of the notebook file.  The “kernelspec” and “language\_info” information is typically already present in the metadata object and the additional notebook metadata data can be added in front :


```
{
	"metadata": {
		"identifier": "eum_211_metop-a_gome-2_no",
		"author": {
			"familyName": "Wagemann",
			"givenName": "Julia"
		},
		"name": "Explore AC SAF Metop-A/B GOME-2 - Tropospheric Nitrogen L2 - Part 1",
		"description": "This notebook is rhe first of two 'data discovery' modules on AC SAF Metop-A GOME-2 data.",
		"image": "../img/211_img.png",
		"license": "https://spdx.org/licenses/MIT",
		"potentialAction": [
			{
				"name": "GitLab",
				"target": "https://gitlab.eumetsat.int/eumetlab/atmosphere/atmosphere/-/blob/master/20_data_exploration/211_Metop-A_GOME-2_NO2Tropo_L2_load_browse.ipynb",
				"provider": {
					"name": "EUMETSAT",
					"email": "training@eumetsat.int"
				}
			},
			{
				"name": "Git",
				"target": "https://gitlab.eumetsat.int/eumetlab/atmosphere/-/blob-master/20_data_exploration/211",
				"provider": {
					"name": "EUMETSAT",
					"email": "training@eumetsat.int"
				}
			},
			{
				"target": "$$$",
				"name": "Google Colab",
				"provider": {
					"name": "EUMETSAT",
					"email": "training@eumetsat.int"
				}
			},
			{
				"target": "$$$",
				"name": "Binder",
				"provider": {
					"name": "EUMETSAT",
					"email": "training@eumetsat.int"
				}
			}
		],
		"keywords": [
			{
				"name": "ATMOSPHERE",
				"inDefinedTermSet": "https://gcmd.earthdata.nasa.gov/kms/concepts/concept_scheme/sciencekeywords"
			},
			{
				"name": "AIR QUALITY",
				"inDefinedTermSet": "https://gcmd.earthdata.nasa.gov/kms/concepts/concept_scheme/sciencekeywords"
			},
			{
				"name": "METOP-A",
				"inDefinedTermSet": "https://gcmd.earthdata.nasa.gov/kms/concepts/concept_scheme/platforms"
			},
			{
				"name": "GOME-2",
				"inDefinedTermSet": "https://gcmd.earthdata.nasa.gov/kms/concepts/concept_scheme/instruments"
			},
			"AC SAF",
			"Nitrogen dioxide (tropospheric column)"
		],
		"kernelspec": {
			"display_name": "Python 3 (ipykernel)",
			"language": "python",
			"name": "python3"
		},
		"language_info": {
			"codemirror_mode": {
				"name": "ipython",
				"version": 3
			},
			"file_extension": ".py",
			"mimetype": "text/x-python",
			"name": "python",
			"nbconvert_exporter": "python",
			"pygments_lexer": "ipython3",
			"version": "3.10.4"
		}
	}
}
```
