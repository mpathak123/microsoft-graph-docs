---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

IGraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

IWorkbookPivotTableCollectionPage pivotTables = graphClient.me().drive().root().workbook().worksheets("{id}").pivotTables()
	.buildRequest()
	.get();

```