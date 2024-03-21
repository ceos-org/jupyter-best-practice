[Previous](objectives-and-needs.md) | [Table of contents](README.md) | [Next](annex/annex-a.md)

***
# 4. JUPYTER NOTEBOOK BEST PRACTICE CONTENT
## 4.1 Notebook description, purpose and discoverability 

The treatment of Notebooks should be highly dependent on their purpose and value.  GitHub reached the milestone of 1 million Jupyter Notebooks in 2020. This proliferation of notebooks within the EO raises a challenge for the community.
The sheer number of available notebooks necessitates a highly selective approach which clearly identifies notebooks of value to be brought under active management. To achieve this the purpose of notebooks must be assessed.
They tend fall into two categories 

1. Notebooks produced as part of the scientific process and record, which are by their very nature static.
1. Notebooks that were created as tools to support the exploitation of EO data.  These have the potential to evolve and be ported across systems. 

Every notebook should have a clear title and abstract which describes who generated it, what it does and its intended purpose. 

Notebooks that were created as part of the scientific process and record, need to clearly and unambiguously describe published data they generated and other research outputs, so they can be associated with them.
If a notebook is expected to generate multiple datasets or research outputs by multiple users it should be considered a tool.

Notebooks that are considered to be tools require additional descriptive information to make them discoverable for new users. Additional information on input datasets, domain/thematic, application, function and skill level are desirable to ensure that notebooks are targeted at the correct communities.
**[ask Ben Loveday for EUMETSAT schema amd reference]**

To achieve a higher level of discoverability, it is recommended that CEOS agencies compile metadata in compliance with the "CEOS Service Discovery Best Practice" [[RD1]](./Introduction.md#RD1).

It is recommended to use the schema.org [[RD2]](./Introduction.md#RD2) (CreativeWork) encoding for the embedded metadata.
See Annex C for more information and an embedded metadata  example.
Adherence to the subsequent sections of this Best practice will generate sufficient metadata to ensure minimal compliance.

## 4.2 Structure, workflow, code and documentation
When embarking on writing a jupyter notebook it is important to fully consider the structure and workflow.
The notebook should present a cohesive and clear narrative to the user breaking the process down in logical manageable steps.
Use descriptive markdown headers to organize your notebook into sections that can be used to easily navigate the notebook and add a table of contents. 

The Jupyter Notebook can be considered to be a hybrid of documentation and software.
As such good software engineering principles should be used when writing and maintaining your jupyter notebooks.
Writers should try to achieve maintainability, dependability, efficiency and usability of code.
While not all principles can be followed due to the ambiguous execution order of cells.
The following should be considered 

- Naming of notebooks: Remember to give your notebook and associated files sensible names which indicate what they are 
- Functions and Modules: Modularise code and use markdown above cells
- Put low-level documentation in code comments.
- Avoid cells in excess of 100 lines
- Unit tests: Use unit testing  for code in line with <https://jupyter-tutorial.readthedocs.io/en/stable/notebook/testing/unittest.html>
- Use standard libraries that can readily be deployed in new environments where possible 

The level of documentation required is determined by the purpose of the notebook.
For notebooks that are scientific records that also ensure the reproducibility of science. Documentation should provide an understandable narrative that guides users through the notebooks and provide a clear explanation of the function of code contained in cells.

However when writing notebooks for use in  Data Science Education or Tool for Data Exploitation authors should adhere to additional advice given in Five Guiding Principles to Make Jupyter Notebooks Fit for Earth Observation Data Education Wagemann et al 2022 <https://www.mdpi.com/2072-4292/14/14/3359>.
Where they advise following  a literate programming paradigm by a text/code ratio of 3 and the use instructional design elements to improve navigation and user experience

## 4.3 Technical dependencies and Virtual Environments

### **Universal and Notebook Specific Dependencies**

All notebooks have the common dependencies that should be explicitly stated  within the header of the main .iypnb file. This is to ensure easy extension, portability and maintenance of the notebooks.

**Platform and Service Dependencies**: All notebooks will run on something whether it is a personal laptop or integrated into a service 

**Language versions** :Jupyter notebooks support Python, Java, R, Julia, Matlab, Octave, Scheme, Processing, Scala, and many other languages. It essential to note not only the language but also the version employed in the notebooks

**Libraries:** Libraries used by the notebook should be clearly identified in the header.  Notebooks are being run on standard machines on data analysis platforms,  sometimes libraries need to be  installed on the fly, for example using conda. When this happens the first cell should be used for that purpose. The installation mechanism should be clearly noted and explained.

**Additional scripts and files**: Frequently notebooks utilize external scripts, shapefiles and other types of file.  The header should contain clear information on their name, location and purpose. Ideally these should be kept in the same repository directory as the notebook  rather than linked to. 

### **Platform/Service Specific Dependencies** 

Many CEOS agencies are running systems and services that support Jupyter Notebooks.  Many notebooks for training and tools for exploitation are now born on these systems.
**[This places a responsibility on systems developers to publish information that will allow identification of a technical dependencies  environment or service which notebooks can cite in their header..  It a recommendation that such information is made available.]]**
While the examples below are not an exhaustive list of service and platforms that can support jupyter.

- **Stand alone computer:** Jupyterlab can be installed and run on personal laptops and computers.
These notebooks are commonly generated off-platform on local computers where the input data is easily downloadable and no large scale processing is required. While you describe the OS and environment in the header a more elegant solution would be to use .yml file to recreate the environment.
This should be kept in the same repository directory as the notebook. Alternatively you could include Ipykernel library in the dependencies and then adding the kernel to jupyter notebook, you can then use the environment in the jupyter notebook if suited to the needs of your notebook..

- **JupyterHub deployed on Data Analysis Platform:** Many CEOS Agencies have deployed  JupyterHub on their data analysis platforms.
Very often this is deployed on specific analysis machine whose environments can be published and version information added to the notebook header for example: <https://help.jasmin.ac.uk/article/4729-jaspy-envs> 

- **OpenDap  and http Services:** In addition to running on a platform notebooks may also rely upon data transfer services run by an archive or platform.
Frequently these services require users to hold accounts or use specific code within cells to enable access. Platforms/archives  should publish up to date information on their services and access requirements.
The notebook should explain the access pathway and link to such information. For example <https://help.ceda.ac.uk/article/4442-ceda-opendap-scripted-interactions> 

- **Zero Install Environments:** Many notebooks are born on or can readily be ported to zero install environments such as Binder Google Collabs or PANGEO. If this is the case use an environment  .yml file which should be archived in the repository directory with your notebook.

**Google Colabs:** 


**ESA PGDS**

**Get example from Simone Mantovani at Workshop**

**Open Data Cube Google Sandbox**

**Get example from Brian Killough/Dave Borge**

**Earth Analytics Interoperability Lab**

**EUMETSAT TrainHub(WGISS-56)**

**MAGEO(WGISS-56)**


## 4.4 Citation, access to and navigation of input data 
For the EO community the most important input will naturally be EO data.  It is therefore essential that the correct data can be identified, located, accessed and navigated successfully  

In the first instance it is important to consider the following 

- In a temporary or permanent location (Data at the end of a project is often unpublished and in a temporary location)
- Has been published or  is a formal citation available.  Has had a DOI issue in line with CEOS persistent identifier Best Practice <https://ceos.org/document_management/Working_Groups/WGISS/Documents/WGISS%20Best%20Practices/CEOS%20Persistent%20Identifier%20Best%20Practice.pdf> 

  It is important note that the location of data used may be different from that indicated by a DOI landing page. 

- Is in the primary archive or being held in a secondary archive or platform 
- What is the data structure and is it different to that of the primary archive
- Are there any tools to support navigation or data cube services to support extraction of specific files

Once the appraisal is complete the following information should be included in notebook headers

- Physical location of data 
- Citation or DOI where available - indicating if this a 3rd Party of data held on a different analysis platform to that of the primary archive.
- Subsection or filetypes with the dataset that the Notebook can be used with 
- Structure of data
- Links to navigation tools and info on data retrieval services (i.e. data cube)
- Information on access restriction and where to apply for access (normally dataset landing page or catalogue record)

## 4.5 Association with archived data
A notebook has the potential to act as documentation or representation information (OAIS) for a dataset in addition to being a tool.
However due to the fragile technical nature of of the software component and therefore assess the role a notebook will perform for a dataset 

- **Tool**: As a tool a notebook can be directly associated with a dataset provided it passes a minimum quality threshold.
It can then be stored in an institution or community repository and linked to the dataset.

- **Documentation:** A project notebook can frequently act as good quality documentation.
If it is solely acting in this role it should immediately be saved with outputs and converted to a PDF before association with a dataset.

- **Representation Information:** A good quality notebook can also be used as representation information and left in an active state.
However critical representation should also be explicitly stated.  For example the format of file should never be inferred from import statements, they should be part of the formal metadata.

## 4.6 Archival, Preservation and Retirement 

It is anticipated that notebooks will both evolve and become technically obsolete over time. It is therefore important to manage the natural lifespan of a notebook.
In addition to the notebook being physically stored in a trusted repository and made discoverable the threat of technical obsolescence must be managed.
A notebook should only be archived and managed in its active state if there is a reasonable expectation that it will remain usable for 5 years.
By recording dependencies the chance of this being the case is greatly increased. Notebooks unlike data should be considered for medium term preservation only.
You will also have removed the most common cause of notebook technical obsolescence.

### **Review of notebooks**
Notebooks under active management should be subject to review.
Some archives will the capability to do this in automated way via unit testing other will ned to take a more manual approach.
This reinforces the need to be highly selective when taking notebooks under active management as opposed to archiving a dormant PDF copy as documentation.
The following should be considered

- Is the notebook still useful and being used 
- Is the  platform/computer environment still available or easily recreated
- Are all services for data acquisition still available and interfaces the same 
- Is the data still available (particularly relevant for commercial data)
- Is there a better notebook available 
- Has the data been physically moved or restructured in any way
- Are you releasing as new data analysis platform or Jupyter hub service if this being used
- If using binder collabs etc are these services is likely to go away 

### **Preservation Strategies** 

Having identified risks and problems and archive or custodian of the notebooks should consider the following preservation strategies and perform a quite cost/benefit analysis of the different approaches.
It is also important to make sure that the notebook header is update the relevant technical/user information information in the header.

- Deprecate the old version and replace with new where appropriate
- Migrate the code to a new version so that it can be run in a new environment/OS/Platform
- Recreate the environment, many data analysis platforms will have the ability to spin up new versions of old machines.
Emulation and Virtualization strategies could also be considered but they would tend to be prohibitively expensive for the sake of an individual notebook.

### **Graceful Retirement**

There will naturally come a point when notebooks should be retired (hibernation strategy). The notebook should save with outputs, a PDF copy taken and marked as dormant. 
This leaves the possibility of the notebook being revived, which should only occur in exceptional case.
Critically this prevents new users becoming discouraged by malfunctioning notebook but allows valuable legacy information to be retained.
Automatic retirement after a specified time period should be considered by repositories.
Retirement of notebooks is essential to avoid a repository of broken things.

## 4.7 Open source software licensing

The Jupyter notebook is a challenging digital object in that it is a combination of documentation (a creative digital object) and code (a software object).
As such we advocate the software carpentry approach to the assessment of IPR and rights to be asserted. <https://reproducible-science-curriculum.github.io/sharing-RR-Jupyter/LICENSE.html> using a two level assessment for the documentation and software.

Unlike software carpentry individuals may wish to restrict access or assert institutional  rights.
As a default the Creative Commons  <https://creativecommons.org/share-your-work/>  and  GNU Software Licences  <https://www.gnu.org/licenses/licenses.en.html>  may be used. 

### **Documentation** 

For the creative and  documentation aspect of the work. We recommend you carry out the following Creative Commons assessment. This covers the most common concerns of depositors 

- **Attribution:** Do you want attribution for your work?
  - Yes. Anyone using my work must include proper attribution.
  - No. Anyone can use my work, even without giving me attribution.
- **Commercial Use:** Do you want to allow others to use your work commercially?
  - Yes. Others can use my work, even for commercial purposes.
  - No. Others can not use my work for commercial purposes.
- **Derivative Works:** Do you want to allow others to remix, adapt, or build upon your work?
  - Yes. Others can remix, adapt, or build upon my work.
  - No. Others may only use my work in unadapted form.
- **Sharing Requirements**:Do you want to allow others to share adaptations of your work under any terms?
  - Yes. Others can share adaptations of my work under any terms.
  - No. Others must use the same CC licence if they adapt my work.

After this assessment  the appropriate creative commons licence may be used.
Alternatively an institutionally approved licence may be use which covers these aspects as a minimum.
These permissions  are key to allowing reuse and extension of a notebook by new users in the community.

### **Software** 

In many case it will be sufficient to use a creative licence by itself.
However for notebooks where there is a  substantial presence of novel code over which you wish to exert copyright, additional code specific licences should be considered.

Where notebooks are published and open for reuse GNU software licences should be considered.
If desired a disclaimer may also be included, below is an example from software carpentry.

“THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.“

## 4.8 Publishing, Versioning and DOI

- **Publishing**: To ensure the broadest possible exploitation of notebooks and associated data notebooks should be deposited in an institutional or trusted public access repository.
Where possible key metadata should be federated to CEOS and other community discovery services **[check this with Yves and Damiano].**
For institution that prefer not running their own repository GitHub <https://github.com/> and Zenodo <https://zenodo.org/> offer a potential solution
- **Versioning and DOI’s  :** Where possible a DOI should be minted for archived notebook and versioning employed.
Versioning has an important role for notebooks and should follow standard software versioning practices.
Notebooks that run on different platforms or have been extended by different groups should be considered distinct from each other rather than versions.
For notebooks that evolve over time or require technical adaptation a standard major/minor versioning convention should be used.
It should noted that Zenodo now supports versioning https://blog.zenodo.org/2017/05/30/doi-versioning-launched/

***
[Previous](objectives-and-needs.md) | [Table of contents](README.md) | [Next](annex/annex-a.md)
