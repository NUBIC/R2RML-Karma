R2RXML mapping files for use in [Karma](http://www.isi.edu/integration/karma/) with data exported from [LatticeGrid](https://github.com/NUBIC/LatticeGrid/).  

For the export files, look at the Rake tasks in the [export.rake](https://github.com/NUBIC/LatticeGrid/blob/develop/lib/tasks/export.rake) file in the LatticeGrid project.

**Tables**

* abstracts
* organizational_units
* investigators
* investigator_abstracts
* investigator_appointments

**Table -> Class**

* abstracts
  * bibo:AcademicArticle - http://purl.org/ontology/bibo/AcademicArticle
  * bibo:Article - http://purl.org/ontology/bibo/Article
  * obo:ERO_0000016 (ClinicalTrial) - http://purl.obolibrary.org/obo/ERO_0000016
  * fabio:Comment - http://purl.org/spar/fabio/Comment
  * vlocal:ComparativeStudy - http://vivo.northwestern.edu/ontology/vlocal#ComparativeStudy
  * vlocal:EvaluationStudy - http://vivo.northwestern.edu/ontology/vlocal#EvaluationStudy
  * bibo:Letter - http://purl.org/ontology/bibo/Letter
* organizational_units
  * vivo:Center - http://vivoweb.org/ontology/core#Center
  * vivo:Department - http://vivoweb.org/ontology/core#AcademicDepartment
  * vivo:Division - http://vivoweb.org/ontology/core#Division

**Attributes**

* table_name
  * Class
    * table_column
      * ontology:attribute

Note: bold and italic attributes are pyTransformed attributes - not from the data export

* abstracts
  * AcademicArticle/Article/ClinicalTrial/Comment/ComparativeStudy/EvaluationStudy/Letter
    * uuid (internal unique identifier for abstracts table)
      * uri
    * Title
      * rdfs:label
    * publication_type
      * vlocal:medlineCategory
    * Volume
      * bibo:volume
    * Issue
      * bibo:issue
    * Pagination (start page)
      * bibo:pageStart
    * Pagination (end page)
      * bibo:pageEnd
    * DOI
      * bibo:doi
    * pubmed
      * bibo:pmid
    * pubmedcentral
      * vivo:pmcid
    * abstract
      * bibo:abstract
    * Full Authors
      * vlocal:fullAuthorList
    * Mesh Terms
      * vlocal:meshTerms
  * Journal
    * Journal OR Published proceedings
      * rdfs:label
    * ISSN
      * bibo:issn
    * **_journal_id_**
      * uri 
  * DateTimeValue
    * Publication Date1
      * vivo:dateTime
    * **_publication_uri_**
      * uri
* organizational_units
  * Center/Division/Department
    * uuid (internal unique identifier for organizational_units table)
      * uri
    * department_id
      * vlocal:DepartmentID
    * division_id
      * vlocal:DivisionID
    * name
      * rdfs:label
    * organization_phone
      * vcard:telephone
    * organization_url
      * vcard:url
* investigators
  * FacultyMember
    * uuid (internal unique identifier for investigators table)
      * uri
    * degrees
      * vcard:honorificSuffix
    * email
      * vcard:email
    * employee_id
      * vlocal:employeeID
    * era_commons_name
      * vivo:eRACommonsId
    * faculty_interests
      * vivo:freetextKeyword
    * faculty_research_summary
      * vivo:researchOverview
    * display_name
      * rdfs:label
    * first_name
      * vcard:givenName
    * last_name
      * vcard:familyName
    * middle_name
      * vivo:middleName
    * title
      * vivo:hrJobTitle
    * username
      * vlocal:netID
* investigator_appointments
  * Position
    * type
      * rdfs:label
    * **_position_uri_**
      * uri
  * FacultyMember
    * investigator_uuid (internal unique identifier for investigators table)
      * uri
  * Organization
    * organizational_unit_uuid (internal unique identifier for organizational_units table)
      * uri
* investigator_abstracts
  * Authorship
    * **_authorship_uri_**
      * uri
  * FacultyMember
    * investigator_uuid (internal unique identifier for investigators table)
      * uri
  * AcademicArticle (this should probably be Article - the superclass)
    * abstract_uuid (internal unique identifier for abstracts table)
      * uri
