<!DOCTYPE html>
<html>
    <head>
        <title>Engineering : Collaboration Services API Documentation</title>
        <link rel="stylesheet" href="styles/site.css" type="text/css" />
        <META http-equiv="Content-Type" content="text/html; charset=UTF-8">
    </head>

    <body class="theme-default aui-theme-default">
        <div id="page">
            <div id="main" class="aui-page-panel">
                <div id="main-header">
                    <div id="breadcrumb-section">
                        <ol id="breadcrumbs">
                            <li class="first">
                                <span><a href="index.html">Engineering</a></span>
                            </li>
                                                </ol>
                    </div>
                    <h1 id="title-heading" class="pagetitle">
                                                <span id="title-text">
                            Engineering : Collaboration Services API Documentation
                        </span>
                    </h1>
                </div>

                <div id="content" class="view">
                    <div class="page-metadata">
                        
        
    
        
    
        
        
            Created by <span class='author'> David Schramm</span>, last modified by <span class='editor'> Walter Davies</span> on Jun 28, 2022
                        </div>
                    <div id="main-content" class="wiki-content group">
                    <p /><style type='text/css'>/*<![CDATA[*/
div.rbtoc1659968352892 {padding: 0px;}
div.rbtoc1659968352892 ul {list-style: disc;margin-left: 0px;}
div.rbtoc1659968352892 li {margin-left: 0px;padding-left: 0px;}

/*]]>*/</style><div class='toc-macro rbtoc1659968352892'>
<ul class='toc-indentation'>
<li><a href='#CollaborationServicesAPIDocumentation-Overview'>Overview</a></li>
<li><a href='#CollaborationServicesAPIDocumentation-IdentityService'>Identity Service</a>
<ul class='toc-indentation'>
<li><a href='#CollaborationServicesAPIDocumentation-RegisterPerson'>Register Person</a></li>
<li><a href='#CollaborationServicesAPIDocumentation-GetPerson'>Get Person</a></li>
</ul>
</li>
<li><a href='#CollaborationServicesAPIDocumentation-DataDiscoveryService'>Data Discovery Service</a>
<ul class='toc-indentation'>
<li><a href='#CollaborationServicesAPIDocumentation-RegisterDocument'>Register Document</a></li>
<li><a href='#CollaborationServicesAPIDocumentation-GetDocumentsbyAvaneerId'>Get Documents by Avaneer Id</a></li>
</ul>
</li>
</ul>
</div><h1 id="CollaborationServicesAPIDocumentation-Overview">Overview</h1><p>The Avaneer Collaboration Services are centralized services intended to help facilitate interoperability between participant Spark Zones. This document describes the RESTful APIs used to communicate with the Avaneer Collaboration Services.</p><span class="confluence-embedded-file-wrapper image-center-wrapper"><img class="confluence-embedded-image image-center" loading="lazy" src="attachments/36208900/48169067.png" data-image-src="attachments/36208900/48169067.png" data-height="615" data-width="971" data-unresolved-comment-count="0" data-linked-resource-id="48169067" data-linked-resource-version="1" data-linked-resource-type="attachment" data-linked-resource-default-alias="Avaneer Network Overview.png" data-base-url="https://avaneerhealth.atlassian.net/wiki" data-linked-resource-content-type="image/png" data-linked-resource-container-id="36208900" data-linked-resource-container-version="37" data-media-id="208ff7f6-8260-4f34-94a6-4caae6c40890" data-media-type="file"></span><p /><p>Avaneer Development Collaboration Services URL: <a href="https://identity.dev.avaneer.shared.healthutilitynetwork.net/" class="external-link" rel="nofollow">https://identity.dev.avaneer.shared.healthutilitynetwork.net</a></p><p><a href="https://datadiscovery.dev.avaneer.shared.healthutilitynetwork.net" class="external-link" rel="nofollow">https://datadiscovery.dev.avaneer.shared.healthutilitynetwork.net</a></p><h1 id="CollaborationServicesAPIDocumentation-IdentityService">Identity Service</h1><h3 id="CollaborationServicesAPIDocumentation-RegisterPerson">Register Person</h3><p>Use this endpoint to register people with the Avaneer Identity Service. Provide your local demographics for the person, and receive an Avaneer ID in response. You will receive the same Avaneer ID back if you register someone more than once. The Avaneer ID is used cross-participant to find the same person in other Spark Zones. Please populate as many optional fields as possible, including as many local identifiers as possible, to help support higher fidelity matching.</p><p><strong>Endpoint</strong></p><div class="code panel pdl" style="border-width: 1px;"><div class="codeContent panelContent pdl">
<pre class="syntaxhighlighter-pre" data-syntaxhighlighter-params="brush: java; gutter: false; theme: Confluence" data-theme="Confluence">POST /api/v1/person</pre>
</div></div><p><strong>Request Body Parameters</strong></p><div class="table-wrap"><table data-layout="default" data-local-id="9633d207-4f53-4814-8442-9ac31140b58c" class="confluenceTable"><colgroup><col style="width: 180.0px;"/><col style="width: 180.0px;"/><col style="width: 111.0px;"/><col style="width: 209.0px;"/></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Type</strong></p></th><th class="confluenceTh"><p><strong>Required</strong></p></th><th class="confluenceTh"><p><strong>Description</strong></p></th></tr><tr><td class="confluenceTd"><p>firstName</p></td><td class="confluenceTd"><p>string</p></td><td class="confluenceTd"><p><img class="emoticon emoticon-tick" data-emoji-id="atlassian-check_mark" data-emoji-shortname=":check_mark:" data-emoji-fallback=":check_mark:" src="images/icons/emoticons/check.png" width="16" height="16" data-emoticon-name="tick" alt="(tick)"/></p></td><td class="confluenceTd"><p /></td></tr><tr><td class="confluenceTd"><p>lastName</p></td><td class="confluenceTd"><p>string</p></td><td class="confluenceTd"><p><img class="emoticon emoticon-tick" data-emoji-id="atlassian-check_mark" data-emoji-shortname=":check_mark:" data-emoji-fallback=":check_mark:" src="images/icons/emoticons/check.png" width="16" height="16" data-emoticon-name="tick" alt="(tick)"/></p></td><td class="confluenceTd"><p /></td></tr><tr><td class="confluenceTd"><p>dob</p></td><td class="confluenceTd"><p>date</p></td><td class="confluenceTd"><p><img class="emoticon emoticon-tick" data-emoji-id="atlassian-check_mark" data-emoji-shortname=":check_mark:" data-emoji-fallback=":check_mark:" src="images/icons/emoticons/check.png" width="16" height="16" data-emoticon-name="tick" alt="(tick)"/></p></td><td class="confluenceTd"><p>Date of birth </p></td></tr><tr><td class="confluenceTd"><p>gender</p></td><td class="confluenceTd"><p>string</p></td><td class="confluenceTd"><p style="text-align: center;"> </p></td><td class="confluenceTd"><p /></td></tr><tr><td class="confluenceTd"><p>city</p></td><td class="confluenceTd"><p>string</p></td><td class="confluenceTd"><p style="text-align: center;"> </p></td><td class="confluenceTd"><p>City or locality</p></td></tr><tr><td class="confluenceTd"><p>postal</p></td><td class="confluenceTd"><p>string</p></td><td class="confluenceTd"><p style="text-align: center;"> </p></td><td class="confluenceTd"><p>Postal or ZIP code</p></td></tr><tr><td class="confluenceTd"><p>phone</p></td><td class="confluenceTd"><p>string</p></td><td class="confluenceTd"><p style="text-align: center;"> </p></td><td class="confluenceTd"><p> </p></td></tr><tr><td class="confluenceTd"><p>maidenName</p></td><td class="confluenceTd"><p>string</p></td><td class="confluenceTd"><p style="text-align: center;"> </p></td><td class="confluenceTd"><p>Mother’s maiden name</p></td></tr><tr><td class="confluenceTd"><p>cityOfBirth</p></td><td class="confluenceTd"><p>string</p></td><td class="confluenceTd"><p style="text-align: center;"> </p></td><td class="confluenceTd"><p>City of birth</p></td></tr><tr><td class="confluenceTd"><p>participantId</p></td><td class="confluenceTd"><p>string</p></td><td class="confluenceTd"><p><img class="emoticon emoticon-tick" data-emoji-id="atlassian-check_mark" data-emoji-shortname=":check_mark:" data-emoji-fallback=":check_mark:" src="images/icons/emoticons/check.png" width="16" height="16" data-emoticon-name="tick" alt="(tick)"/></p></td><td class="confluenceTd"><p>Romulus, Vulcan, etc</p></td></tr><tr><td class="confluenceTd"><p>localIdentifier</p></td><td class="confluenceTd"><p>Object Array</p></td><td class="confluenceTd"><p> </p></td><td class="confluenceTd"><p> </p></td></tr><tr><td class="confluenceTd"><p>localIdentifier.type</p></td><td class="confluenceTd"><p>ENUM</p></td><td class="confluenceTd"><p /></td><td class="confluenceTd"><p>Use codes as defined here: <a href="https://build.fhir.org/valueset-identifier-type.html" data-card-appearance="inline" class="external-link" rel="nofollow">https://build.fhir.org/valueset-identifier-type.html</a> </p><p>e.g. Medical record number, Driver's license number, Social Beneficiary Identifier (SSN)</p></td></tr><tr><td class="confluenceTd"><p>localIdentifier.value</p></td><td class="confluenceTd"><p>string</p></td><td class="confluenceTd"><p /></td><td class="confluenceTd"><p /></td></tr></tbody></table></div><p><strong>Sample Request</strong></p><div class="code panel pdl" style="border-width: 1px;"><div class="codeContent panelContent pdl">
<pre class="syntaxhighlighter-pre" data-syntaxhighlighter-params="brush: java; gutter: false; theme: Confluence" data-theme="Confluence">{
    &quot;firstName&quot;: &quot;John&quot;,
    &quot;lastName&quot;: &quot;Doe&quot;,
    &quot;dob&quot;: &quot;1930-01-21&quot;,
    &quot;gender&quot;: &quot;unknown&quot;,
    &quot;city&quot;: &quot;St Columbans&quot;,
    &quot;postal&quot;: &quot;57850&quot;,
    &quot;phone&quot;: &quot;(366)-564-1253&quot;,
    &quot;maidenName&quot;: &quot;Rahmel&quot;,
    &quot;cityOfBirth&quot;: &quot;Wilmar&quot;,
    &quot;participantId&quot;: &quot;Romulus&quot;,
    &quot;localIdentifier&quot;: [{
        &quot;type&quot;: &quot;MR&quot;,
        &quot;value&quot;: &quot;123456&quot;
    }]
}</pre>
</div></div><p><strong>Sample Response(s)</strong></p><div class="code panel pdl" style="border-width: 1px;"><div class="codeContent panelContent pdl">
<pre class="syntaxhighlighter-pre" data-syntaxhighlighter-params="brush: java; gutter: false; theme: Confluence" data-theme="Confluence">HTTP Response Code: 201 Created
{
    &quot;avaneerId&quot;: &quot;97c08a2a-fb47-4499-8466-9d5db3831642&quot;
}

HTTP Response Code: 400 Bad Request
{
    &quot;errors&quot;: [
        {
            &quot;field&quot;: &quot;FirstName&quot;,
            &quot;msg&quot;: &quot;This field is required&quot;
        }
    ]
}

HTTP Response Code: 400 Bad Request
{
    &quot;message&quot;: &quot;JSON syntax invalid&quot;
}</pre>
</div></div><h3 id="CollaborationServicesAPIDocumentation-GetPerson">Get Person</h3><p>Use this endpoint to get the Avaneer ID for an existing person by providing a local ID, or provide an Avaneer ID to confirm that the Avaneer ID is already registered with Avaneer.</p><p><strong>Endpoint</strong></p><div class="code panel pdl" style="border-width: 1px;"><div class="codeContent panelContent pdl">
<pre class="syntaxhighlighter-pre" data-syntaxhighlighter-params="brush: java; gutter: false; theme: Confluence" data-theme="Confluence">GET /api/v1/person?avaneerId=:avaneerId
GET /api/v1/person?localId=:localId
GET /api/v1/person?localId=:localId&amp;type=:value</pre>
</div></div><p><strong>Query String Parameters</strong></p><div class="table-wrap"><table data-layout="default" data-local-id="ed8e399c-6db9-429a-8b64-e3576f86d013" class="confluenceTable"><colgroup><col style="width: 180.0px;"/><col style="width: 180.0px;"/><col style="width: 111.0px;"/><col style="width: 209.0px;"/></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Type</strong></p></th><th class="confluenceTh"><p><strong>Required</strong></p></th><th class="confluenceTh"><p><strong>Description</strong></p></th></tr><tr><td class="confluenceTd"><p>avaneerId</p></td><td class="confluenceTd"><p>string</p></td><td class="confluenceTd"><p>Require one of: only avaneerId OR localId</p></td><td class="confluenceTd"><p>e.g. 51f86a43-8a49-431b-942e-f30b9ddc2b72</p></td></tr><tr><td class="confluenceTd"><p>localId</p></td><td class="confluenceTd"><p>string</p></td><td class="confluenceTd"><p>Require one of: only avaneerId OR localId</p></td><td class="confluenceTd"><p>e.g. 1234</p></td></tr><tr><td class="confluenceTd"><p>type</p></td><td class="confluenceTd"><p>string</p></td><td class="confluenceTd"><p>optional</p></td><td class="confluenceTd"><p>Used when querying by localId only.</p><p>Use codes as defined here: <a href="https://build.fhir.org/valueset-identifier-type.html" data-card-appearance="inline" class="external-link" rel="nofollow">https://build.fhir.org/valueset-identifier-type.html</a> </p><p>e.g. Medical record number, Driver's license number, Social Beneficiary Identifier (SSN)</p></td></tr></tbody></table></div><p><strong>Sample Response(s)</strong></p><div class="code panel pdl" style="border-width: 1px;"><div class="codeContent panelContent pdl">
<pre class="syntaxhighlighter-pre" data-syntaxhighlighter-params="brush: java; gutter: false; theme: Confluence" data-theme="Confluence">HTTP Response Code: 200 OK
{
    &quot;avaneerIds&quot;: [&quot;51f86a43-8a49-431b-942e-f30b9ddc2b72&quot;]
}

HTTP Response Code: 404 Not Found
{
    &quot;error&quot;: &quot;No data found for {&quot;avaneerId&quot;|&quot;localId&quot;}: 51f86a43-8a49-431b-942e-f30b9ddc2b73&quot;
}

HTTP Response Code: 400 Bad Request
{
    &quot;error&quot;: &quot;Invalid query parameter used. Please use only &#39;avaneerId&#39; or &#39;localId&#39;.&quot;
}</pre>
</div></div><h1 id="CollaborationServicesAPIDocumentation-DataDiscoveryService">Data Discovery Service</h1><h3 id="CollaborationServicesAPIDocumentation-RegisterDocument">Register Document</h3><p>Use this endpoint to register the location of documents with Avaneer. Store FHIR Resources in the FHIR server in your Spark Zone, and store the URL pointing to that document in Avaneer’s Data Discovery Service, so that other participants on the network can discover document locations by Avaneer ID.</p><p><strong>Endpoint</strong></p><div class="code panel pdl" style="border-width: 1px;"><div class="codeContent panelContent pdl">
<pre class="syntaxhighlighter-pre" data-syntaxhighlighter-params="brush: java; gutter: false; theme: Confluence" data-theme="Confluence">POST /api/v1/resources</pre>
</div></div><p><strong>Request Body Parameters</strong></p><div class="table-wrap"><table data-layout="default" data-local-id="bc3959b1-facd-4677-93e2-25011b7815e1" class="confluenceTable"><colgroup><col style="width: 180.0px;"/><col style="width: 180.0px;"/><col style="width: 111.0px;"/><col style="width: 209.0px;"/></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Type</strong></p></th><th class="confluenceTh"><p><strong>Required</strong></p></th><th class="confluenceTh"><p><strong>Description</strong></p></th></tr><tr><td class="confluenceTd"><p>avaneerId</p></td><td class="confluenceTd"><p>string</p></td><td class="confluenceTd"><p><img class="emoticon emoticon-tick" data-emoji-id="atlassian-check_mark" data-emoji-shortname=":check_mark:" data-emoji-fallback=":check_mark:" src="images/icons/emoticons/check.png" width="16" height="16" data-emoticon-name="tick" alt="(tick)"/></p></td><td class="confluenceTd"><p>e.g. 51f86a43-8a49-431b-942e-f30b9ddc2b72</p></td></tr><tr><td class="confluenceTd"><p>participantId</p></td><td class="confluenceTd"><p>string</p></td><td class="confluenceTd"><p><img class="emoticon emoticon-tick" data-emoji-id="atlassian-check_mark" data-emoji-shortname=":check_mark:" data-emoji-fallback=":check_mark:" src="images/icons/emoticons/check.png" width="16" height="16" data-emoticon-name="tick" alt="(tick)"/></p></td><td class="confluenceTd"><p>Necessary until Authentication is added in Q2</p></td></tr><tr><td class="confluenceTd"><p>resources</p></td><td class="confluenceTd"><p>Object array</p></td><td class="confluenceTd"><p><img class="emoticon emoticon-tick" data-emoji-id="atlassian-check_mark" data-emoji-shortname=":check_mark:" data-emoji-fallback=":check_mark:" src="images/icons/emoticons/check.png" width="16" height="16" data-emoticon-name="tick" alt="(tick)"/></p></td><td class="confluenceTd"><p>One or multiple resource locations can be registered</p></td></tr><tr><td class="confluenceTd"><p>resources.id</p></td><td class="confluenceTd"><p>string</p></td><td class="confluenceTd"><p><img class="emoticon emoticon-tick" data-emoji-id="atlassian-check_mark" data-emoji-shortname=":check_mark:" data-emoji-fallback=":check_mark:" src="images/icons/emoticons/check.png" width="16" height="16" data-emoticon-name="tick" alt="(tick)"/></p></td><td class="confluenceTd"><p>Identifier for the resource as provided by your Spark Zone’s FHIR server</p></td></tr><tr><td class="confluenceTd"><p>resources.type</p></td><td class="confluenceTd"><p>string</p></td><td class="confluenceTd"><p><img class="emoticon emoticon-tick" data-emoji-id="atlassian-check_mark" data-emoji-shortname=":check_mark:" data-emoji-fallback=":check_mark:" src="images/icons/emoticons/check.png" width="16" height="16" data-emoticon-name="tick" alt="(tick)"/></p></td><td class="confluenceTd"><p><a href="https://build.fhir.org/resourcelist.html" data-card-appearance="inline" class="external-link" rel="nofollow">https://build.fhir.org/resourcelist.html</a> </p></td></tr><tr><td class="confluenceTd"><p>resources.url</p></td><td class="confluenceTd"><p>string</p></td><td class="confluenceTd"><p><img class="emoticon emoticon-tick" data-emoji-id="atlassian-check_mark" data-emoji-shortname=":check_mark:" data-emoji-fallback=":check_mark:" src="images/icons/emoticons/check.png" width="16" height="16" data-emoticon-name="tick" alt="(tick)"/></p></td><td class="confluenceTd"><p>“Global Avaneer URL”, pointing to the location of document in your Spark Zone FHIR server</p></td></tr></tbody></table></div><p><strong>Sample Request</strong></p><div class="code panel pdl" style="border-width: 1px;"><div class="codeContent panelContent pdl">
<pre class="syntaxhighlighter-pre" data-syntaxhighlighter-params="brush: java; gutter: false; theme: Confluence" data-theme="Confluence">{
        &quot;avaneerId&quot;: &quot;51f86a43-8a49-431b-942e-f30b9ddc2b72&quot;,
        &quot;participantId&quot;: &quot;1234&quot;,
        &quot;resources&quot;: [
            {
                &quot;type&quot;: &quot;Person&quot;,
                &quot;id&quot;: &quot;2ae4&quot;,
                &quot;url&quot;: &quot;https://www.fhirserverurl.net/person/123&quot;
            },
            {
                &quot;type&quot;: &quot;Coverage&quot;,
                &quot;id&quot;: &quot;5dw3&quot;,
                &quot;url&quot;: &quot;https://www.fhirserverurl.net/coverage/123&quot;
            },
            {
                &quot;type&quot;: &quot;Coverage&quot;,
                &quot;id&quot;: &quot;1yh5&quot;,
                &quot;url&quot;: &quot;https://www.fhirserverurl.net/coverage/2ab&quot;
            }
        ]
    }</pre>
</div></div><p><strong>Sample Response(s)</strong></p><div class="code panel pdl" style="border-width: 1px;"><div class="codeContent panelContent pdl">
<pre class="syntaxhighlighter-pre" data-syntaxhighlighter-params="brush: java; gutter: false; theme: Confluence" data-theme="Confluence">HTTP Response Code: 201 Created
{
    &quot;message&quot;: &quot;Successfully registered&quot;
}

HTTP Response Code: 400 Bad Request
{
    &quot;errors&quot;: [
        {
            &quot;field&quot;: &quot;AvaneerID&quot;,
            &quot;msg&quot;: &quot;Invalid uuid&quot;
        },
        {
            &quot;field&quot;: &quot;Resources&quot;,
            &quot;msg&quot;: &quot;This field is required&quot;
        }
    ]
}</pre>
</div></div><h3 id="CollaborationServicesAPIDocumentation-GetDocumentsbyAvaneerId">Get Documents by Avaneer Id</h3><p>Use this endpoint to get document locations from participants across the Avaneer network. This endpoint returns URLs only. To retrieve the document itself, query the URL returned by the Data Discovery Service.</p><p><strong>Endpoint</strong></p><div class="code panel pdl" style="border-width: 1px;"><div class="codeContent panelContent pdl">
<pre class="syntaxhighlighter-pre" data-syntaxhighlighter-params="brush: java; gutter: false; theme: Confluence" data-theme="Confluence">GET /api/v1/resources?avaneerId=:avaneerId&amp;participantId=:participantId
GET /api/v1/resources?avaneerId=:avaneerId&amp;participantId=:participantId&amp;type=:type</pre>
</div></div><p><strong>Query String Parameters</strong></p><div class="table-wrap"><table data-layout="default" data-local-id="1e7e0a16-a4b6-4f7f-8de2-af2b45be9149" class="confluenceTable"><colgroup><col style="width: 180.0px;"/><col style="width: 180.0px;"/><col style="width: 111.0px;"/><col style="width: 209.0px;"/></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Type</strong></p></th><th class="confluenceTh"><p><strong>Required</strong></p></th><th class="confluenceTh"><p><strong>Description</strong></p></th></tr><tr><td class="confluenceTd"><p>avaneerId</p></td><td class="confluenceTd"><p>string</p></td><td class="confluenceTd"><p><img class="emoticon emoticon-tick" data-emoji-id="atlassian-check_mark" data-emoji-shortname=":check_mark:" data-emoji-fallback=":check_mark:" src="images/icons/emoticons/check.png" width="16" height="16" data-emoticon-name="tick" alt="(tick)"/></p></td><td class="confluenceTd"><p>One and only one</p></td></tr><tr><td class="confluenceTd"><p>participantId</p></td><td class="confluenceTd"><p>string</p></td><td class="confluenceTd"><p><img class="emoticon emoticon-tick" data-emoji-id="atlassian-check_mark" data-emoji-shortname=":check_mark:" data-emoji-fallback=":check_mark:" src="images/icons/emoticons/check.png" width="16" height="16" data-emoticon-name="tick" alt="(tick)"/></p></td><td class="confluenceTd"><p>Necessary until Authentication is added in Q2</p></td></tr><tr><td class="confluenceTd"><p>type</p></td><td class="confluenceTd"><p>string</p></td><td class="confluenceTd"><p>optional</p></td><td class="confluenceTd"><p>Use codes as defined here: <a href="https://build.fhir.org/valueset-identifier-type.html" data-card-appearance="inline" class="external-link" rel="nofollow">https://build.fhir.org/valueset-identifier-type.html</a> </p></td></tr></tbody></table></div><p><strong>Sample Response(s)</strong></p><div class="code panel pdl" style="border-width: 1px;"><div class="codeContent panelContent pdl">
<pre class="syntaxhighlighter-pre" data-syntaxhighlighter-params="brush: java; gutter: false; theme: Confluence" data-theme="Confluence">HTTP Response Code: 200 OK
{
    &quot;avaneerId&quot;: &quot;3a1721f8-727f-4cb3-8f53-1cf578eb4a60&quot;,
    &quot;resources&quot;: [
        {
            &quot;participantId&quot;: &quot;1234&quot;,
            &quot;type&quot;: &quot;Person&quot;,
            &quot;id&quot;: &quot;123&quot;,
            &quot;url&quot;: &quot;https://www.fhirserverurl.net/person/123&quot;
        },
        {
            &quot;participantId&quot;: &quot;1234&quot;,
            &quot;type&quot;: &quot;Coverage&quot;,
            &quot;id&quot;: &quot;234&quot;,
            &quot;url&quot;: &quot;https://www.fhirserverurl.net/coverage/234&quot;
        },
        {
            &quot;participantId&quot;: &quot;5678&quot;,
            &quot;type&quot;: &quot;PaymentNotice&quot;,
            &quot;id&quot;: &quot;1111&quot;,
            &quot;url&quot;: &quot;https://www.anotherfhirserverurl.net/payment/1111&quot;
        },
        {
            &quot;participantId&quot;: &quot;7890&quot;,
            &quot;type&quot;: &quot;Claim&quot;,
            &quot;id&quot;: &quot;DEF&quot;,
            &quot;url&quot;: &quot;https://www.serverfhir.net/claim/DEF&quot;
        }
    ]
}

HTTP Response Code: 404 Not Found
{
    &quot;error&quot;: &quot;No data found for avaneerId: 3a1721f8-727f-4cb3-8f53-1cf578eb4a60&quot;
}

HTTP Response Code: 400 Bad Request
{
    &quot;errors&quot;: [
        {
            &quot;field&quot;: &quot;AvaneerId&quot;,
            &quot;msg&quot;: &quot;Invalid uuid&quot;
        },
        {
            &quot;field&quot;: &quot;ParticipantId&quot;,
            &quot;msg&quot;: &quot;This field is required&quot;
        }
    ]
}</pre>
</div></div>
                    </div>

                                        <div class="pageSection group">
                        <div class="pageSectionHeader">
                            <h2 id="attachments" class="pageSectionTitle">Attachments:</h2>
                        </div>

                        <div class="greybox" align="left">
                                                            <img src="images/icons/bullet_blue.gif" height="8" width="8" alt=""/>
                                <a href="attachments/36208900/48169067.png">Avaneer Network Overview.png</a> (image/png)
                                <br/>
                                                    </div>
                    </div>
                    
                 
                </div>             </div> 
            <div id="footer" role="contentinfo">
                <section class="footer-body">
                    <p>Document generated by Confluence on Aug 08, 2022 10:19</p>
                    <div id="footer-logo"><a href="http://www.atlassian.com/">Atlassian</a></div>
                </section>
            </div>
        </div>     </body>
</html>
