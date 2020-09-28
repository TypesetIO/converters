# Typeset Public Converters and API

<!-- TOC depthFrom:1 depthTo:2 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Typeset Converter for Academic Publishers and Journals](#typeset-converters)
    - [Preamble](#preamble)
    - [Meta](#meta)
    - [API overview](#converter-api-overview)

<!-- /TOC -->


## Preamble

The Typeset CONVERTER API is [a variety of tools and APIs](https://typeset.io/for-publishers/convert/pdf-to-jats-xml/) that allow journals and academic publishers to convert:
- PDF to JATS XML
- PDF to CrossRef XML
- PDF to PubMed XML
- PDF to SciELO XML
- PDF to Redalyc XML
- PDF to Datatcite XML
- PDF to DOAJ XML
- Word to JATS XML
- Word to CrossRef XML
- Word to PubMed XML
- Word to SciELO XML
- Word to Redalyc XML
- Word to Datatcite XML
- Word to DOAJ XML
- JATS XML to PDF (API available)
- CrossRef XML to PDF (API available)
- PubMed XML to PDF (API available)
- SciELO XML to PDF (API available)
- Redalyc XML to PDF (API available)
- Datatcite XML to PDF (API available)
- DOAJ XML to PDF (API available)

## Meta

### Support

Check our twitter feeds at [TypesetIO](https://twitter.com/typesetio). 
Write to us at support@typeset.io

### Privacy

We also have a [privacy policy](https://typeset.io/t/privacy/).

### Etiquette

We have provided certain public, open, and free converters for all. 

And we don't want to unnecessarily burden developers (or ourselves) with requests overloading that chokes our production system.
For that to work, we ask that you be polite and try not to do anything that will take the public converters down or otherwise make it unusable for others. 

Specifically, we encourage the following polite behaviour:
- Don't run the conversion of the same file multiple times.
- If the conversion fails, that's fine. Please hold on for few hours. These are public systems.
- The feature set in the Public converters is limited. For instance, you would not see a perfect XML generation happening or data would be missing. This is expected.
- If you want a complete accurate production - ready conversion, we recommend our [Typeset Publisher Solution](www.typeset.io/for-publishers/?source=github)


### more reliable service is priority
- report problems and/or ask questions on our [issue tracker](https://github.com/TypesetIO/converters/issues).
- We reserve the right to impose rate limits and/or to block clients that are disrupting the public service.


##### Frequently anticipated questions on the Public converters:

**Q:** Will you spam me with marketing info once you have our contact info?

**A:** No. We will only use it to contact you about problems with your generated XML, if you have any.


**Q:** Does the contact info have to be a real name?

**A:** No. As long as somebody actually receives and pays attention to email at the address, it can be pseudo-anonymous, or whatever.



#### Public Converters Rate limits

Our Public Converters version has rate limits. You can do conversion for 2 files in a day after which you will be blocked. 
From time to time we need to impose rate limits to ensure that the free converter is usable by all. 


### Use for production services

What if you want to use our API for a production service. 
Well, good news. Write us an email to "journals@typeset.io" and someone from our Sales team will reach out to you within 24 hours.
Our Premium Service level offering is known as Typeset Publisher Solution. This service provides you with access to high quality conversion within seconds.

#### Authorization token for Typeset Publisher Solution

When you sign up for the Publisher Solution, you will be issued an API token and also provided access to a Publisher Account. The Publisher Account can only be accessed by you and your Editorial Team.


## Converter API overview

- RESTFUL API. 
- Results returned in JSON.
- Support for both HTTP and HTTPS

Encode your URLs.
The example mentioned below is for JATS XML to PDF conversion. 

Using the URL:

`https://api.typeset.io/convert/jats-xml-to-pdf/?token=32190dnfasd-09123nkl

Note that the token is fake here, and would not work, if you tried.
Once we onboard you as part of the Typeset Publisher Solution, you would be provided with a real token.

Will return the following result:

    {
      status: "ok",
      message-type: "jats-xml-to-pdf",
      message-version: "1.0.0",
      message: {
        status: "success",
        details: {
          id: "1lasdf-213",
          label: "JATS XML to PDF",
          input_file: "determination-of-arti-23-infra.pdf",
          output_file: "determination-of-arti-23-infra.xml",
          metadata: {
              updated_at: "27-09-2020,
              publisher_name: "NAER journal"
          }
        }
      }
    }

## Result types

All results are returned in JSON in the following form:

- Singletons (Singletons are single results.)
- Headers-only (quickly determine "existence" of a singleton)
- Lists (contains multiple entries)

The mime-type for API results is `application/vnd.typeset-api-message+json`
