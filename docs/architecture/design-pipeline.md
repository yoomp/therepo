# Pipeline Architecture Diagram


  CSV[CSV source data] --> |Data validation / ingestion fields| CSVBronze[CSV Bronze layer]
  CSVBronze --> |Standardising e.g. formats, units, naming conventions, data types etc.| CSVSilver[CSV Silver layer]
  CSVBronze --> |Failures on standardising data| CSVQuar[Quarantine]
  CSVSilver --> |Access controls, reports, filtering sensitive data| CSVGold[CSV Gold layer]

  JSON[JSON source data] --> |Data validation / ingestion fields| JSONBronze[JSON Bronze layer]
  JSONBronze --> |Standardising e.g. formats, units, naming conventions, data types etc.| JSONSilver[JSON Silver layer]
  JSONBronze --> |Failures on standardising data| JSONQuar[Quarantine]
  JSONSilver --> |Access controls, reports, filtering sensitive data| JSONGold[JSON Gold layer]

  Text[Text source data] --> |Data validation / ingestion fields| TextBronze[Text Bronze layer]
  TextBronze --> |Standardising e.g. formats, units, naming conventions, data types etc.| TextSilver[Text Silver layer]
  TextBronze --> |Failures on standardising data| TextQuar[Quarantine]
  TextSilver --> |Access controls, reports, filtering sensitive data| TextGold[Text Gold layer]

  Excel[Excel source data] --> |Data validation / ingestion fields| ExcelBronze[Excel Bronze layer]
  ExcelBronze --> |Standardising e.g. formats, units, naming conventions, data types etc.| ExcelSilver[Excel Silver layer]
  ExcelBronze --> |Failures on standardising data| ExcelQuar[Quarantine]
  ExcelSilver --> |Access controls, reports, filtering sensitive data| ExcelGold[Excel Gold layer]

  CSVGold --> Datamart[Datamart]
  JSONGold --> Datamart[Datamart]
  TextGold --> Datamart[Datamart]
  ExcelGold --> Datamart[Datamart]
