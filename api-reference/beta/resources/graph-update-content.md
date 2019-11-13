---
title: "Update existing documentation"
description: "Update existing documentation"
localization_priority: Normal
author: "davidmu1"
ms.prod: "microsoft-identity-platform"
doc_type: resourcePageType
---

# Update existing documentation 


The following table lists the optional and required steps if you are updating or adding to workload APIs.

| Step | Required | Owner |
| ---- | -------- | ----- |
| 1 – Set up environment | Yes | PM, Developer |
| 2 – Create or update an API topic | No | PM, Developer |
| 3 – Add properties to a resource | No | PM, Developer |
| 4 – Add table of contents (TOC) entries | No | PM, Developer, Content Developer |
| 5 – Add change log entries | Yes | PM, Developer, Content Developer |
| 6 – Perform technical review | Yes | PM, Developer |
| 7 – Publish | Yes | Content Developer, Editor |

## Set up environment

1. **(Required)** Notify the Content Development team that the documentation process is beginning for workload APIs and when the documentation is expected to go live. This may be a work item created in the documentation queue, or it might be an email sent to a Content Developer assigned to support the workload.
2. **(Optional)** If you are new to creating documentation, make sure that you are set up to use Markdown and GitHub. For more information about using GitHub and writing in Markdown, see:
    - [Docs Markdown Reference](https://review.docs.microsoft.com/help/contribute/markdown-reference?branch=master)
    - [Download Visual Studio Code](https://code.visualstudio.com/)
3. **(Required)** Create a working branch in GitHub. Always add or update content through a pull request from a personal branch. Do not use the Upload files button on GitHub. If you are submitting a set of changes, be sure to make all your changes in a single branch and not multiple separate branches. This improves processing and publishing efficiency. For more information, see the [Setting up your fork of the repository](https://msgo.azurewebsites.net/add/document/guidelines/manage-your-documentation.html#setting-up-your-fork-of-the-repository) and the [Create a new branch](https://msgo.azurewebsites.net/add/document/guidelines/manage-your-documentation.html#create-a-new-branch) sections of [Working with GitHub](https://msgo.azurewebsites.net/add/document/guidelines/manage-your-documentation.html).

## Create or update an API topic

1. **(Optional)** If a new API or resource has been introduced into your workload or a large scale update needs to be made to existing API articles (where overwriting the existing articles is preferred over updating them), create initial pages using the stub generator scripts. Microsoft Graph uses CSDL (and XML format) for defining its API surface. The stub generator scripts produce stub markdown files based on the definitions in the CSDL file. Do not change the file names that are generated by the tool. For more information, see [Use the Microsoft Graph REST API docs stub generator](https://msgo.azurewebsites.net/add/document/guidelines/stub-generator.html#scenario-and-usage). 

    Each version of an API has its own reference page. For example, there is one message.md file for the message entity in v1.0, and another message.md file for beta. Usually, an API debuts in beta, so you would create a topic only for beta.

    After you run the stub generation, do not change the generated file name. Do not reorder sections in a generated topic. Do not customize generated table columns.

2. **(Required)** Use the following guidance to document the API:
    - Start by using a single sentence to summarize the purpose of the API. Add links to any referenced resources.
    - Provide any information relevant to using the API, before the Permissions section.
    - Fill in the applicable permissions.
    - For the HTTP request, select the syntax lines that apply to your API offering, remove other generated lines that don’t.
    - Document applicable parameters, such as OData query parameters, path parameters, and function parameters. You may need to customize parameter documentation under the appropriate section. Some sections do not always apply and are not generated, for example, a DELETE operation topic doesn’t include an “Optional query parameters” section.
    - Add request headers that apply, stating which ones are required or optional. Remove those headers that do not apply, for example, content-type for an API that doesn’t use a request body.
    - Include request body properties that apply. Enhance descriptions where helpful.
    - Make sure to clarify any returned object in the response and provide a link to its topic. If applicable, you can include error code information here as well, by adding an H3 Errors section.
    - Replace the existing generated pseudo examples with ones that are common use cases of your API. Provide real-looking property values, not pseudo property values. Make sure you tag examples appropriately to enable API Doctor to maintain their currency over time. There is no action item for authors adding or updating REST examples to enable the interactive try-it experience embedded in an API topic, or to add or update language-dependent example code snippets. The weekly automated sweep on Tuesdays is intended to make the necessary updates to maintain these two experiences.
    - Provide links in a **See also** section to related concept topics, or other related API topics that haven’t been linked to in context earlier in the topic. This section is optional.
    - In the methods section of the parent resource type topic, make sure the API method is part of the methods table, and has a description.
3. **(Required)** Copy the API and resource files that you created to the appropriate folders in the working branch that you created.
4. **(Required)** Create the pull request (PR). Set the label of the pull request to do not merge. When you receive the build verification mail, you’ll be able to preview your content by navigating to your personal branch on the review site: https://review.docs.microsoft.com/en-us/graph/overview?branch=master . (Change “master” to the name of your branch.)  For more information, see the [Add new content or edit existing content](https://msgo.azurewebsites.net/add/document/guidelines/manage-your-documentation.html#add-new-content-or-edit-existing-content) and the [Submit a pull request to the main repository](https://msgo.azurewebsites.net/add/document/guidelines/manage-your-documentation.html#submit-a-pull-request-to-the-main-repository) sections of [Working with GitHub](https://msgo.azurewebsites.net/add/document/guidelines/manage-your-documentation.html).

## Add properties to a resource

1. **(Optional)** Create initial pages using the stub generator scripts. Microsoft Graph uses CSDL (and XML format) for defining its API surface. The stub generator scripts produce stub markdown files based on the definitions in the CSDL file. Do not change the file names that are generated by the tool. For more information, see [Use the Microsoft Graph REST API docs stub generator](https://msgo.azurewebsites.net/add/document/guidelines/stub-generator.html#scenario-and-usage). 

    Each version of an API has its own reference page. For example, there is one message.md file for the message entity in v1.0, and another message.md file for beta. Usually, an API debuts in beta, so you would create a topic only for beta.

    After you run the stub generation, do not change the generated file name. Do not reorder sections in a generated topic. Do not customize generated table columns.

    Provide relevant details to the property descriptions. Note that if there is more to provide for the description than a table cell can reasonably contain for readability, or, the possible values for the property warrant further explanation, consider creating a separate section with an H3 heading following the properties table. For example, the group visibility options section is an H3 section under the H2 Properties section in the group topic.

2. **(Optional)** Manually update the **Properties** section by adding or updating a table row for each property, providing the type and relevant description. Again, similar to the generation approach, if there’s more content than a table cell can reasonably display, consider creating a separate section with an H3 heading following the properties table.
Update the JSON that is enclosed in the HTML comment. In particular, make sure the following attributes are specified correctly where applicable: @odata.type, baseType, keyProperty, openType, optionalProperties See details for [how to describe a resource in a JSON object](https://msgo.azurewebsites.net/add/document/guidelines/api-doctor-validate-examples.html#describe-a-resource-example-request-or-example-response-in-a-json-object). In the actual JSON definition, add/update the property name and type.
3. **(Optional)** Include properties in existing examples where applicable, for example, if a GET operation includes the properties in its response. If helpful to customers, or if the new properties are for a compelling scenario, create new examples to show usage of the new properties.
4. **(Optional)** If you are adding a navigation property, do the same steps as adding a property as listed above, except you should add the navigation property to the Relationships section, and not to the Properties section. In the **JSON representation** section, at the top of the section, add the navigation property to the list of optionalProperties. Note: API Doctor doesn’t currently rely on navigation properties being defined there.

## Add table of contents entries

**(Required)** Open either the beta or v1.0 toc.yml file in the branch that you created and add table of contents (TOC) entries for the APIs that you are adding. The TOC helps developers locate conceptual and API pages. For more information, see [Microsoft Graph TOC and Topic Title Guidelines](https://msgo.azurewebsites.net/add/document/guidelines/toc-and-topic-title.html).  

Note that sometimes a method is relevant and exposed in more than one context in the TOC, to show the potential of Microsoft Graph. For example, a user-centric method like sendMail appears under the Users >> Mail node and under the Mail >> Message node.
Think where your documentation should appear in the TOC, and the TOC titles you want to use. Base this off the existing TOC to maintain consistency across all the content. For more information about how content is structured, see [Microsoft Graph IA principles](https://msgo.azurewebsites.net/add/document/guidelines/ia-principles.html).

## Add change log entries

**(Required)** Add change log entries for the APIs and resources that you are adding. For more information, see [Microsoft Graph changelog guidelines](https://msgo.azurewebsites.net/add/document/guidelines/changelog.html).

## Perform technical review

**(Required)** When requesting changes to the content, use the [GitHub review feature](https://help.github.com/en/articles/about-pull-request-reviews) and select **Request changes**. This indicates that the PR is not yet ready to merge. When your feedback has been addressed, change the review status on the PR to **Approved**. Only PRs with a status of **Approved** are merged even if the contributor has indicated that the PR is ready to merge.

The technical review generally creates several actions and changes. The PR review process can be time consuming; however, it is necessary to ensure technical accuracy, compliance, and completeness. If you are on the review chain, you will need to approve the PR before it can be published. When the content has been reviewed and revised to be technically accurate, set the label to **content review**.

## Publish

**(Required)** Before the API documentation can be published, a content review is performed by the Content Developer and the Editor who merges PRs. After the review process is complete, incorporate any feedback that was provided in the PR. When all feedback has been incorporated, reviewers have signed off, and the APIs have been released live, set the label to **ready to merge**, enter **sign-off** as a comment, and then the articles will be published. 

PRs that are ready to merge are merged before 3 PM. All API Doctor and OPS build validation tests must pass before merging. At or after 3 PM daily, all PRs that have been merged into the master branch are pulled into the live branch to publish to the site.