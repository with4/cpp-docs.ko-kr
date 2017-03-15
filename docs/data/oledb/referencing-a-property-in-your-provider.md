---
title: "공급자의 속성 참조 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB 공급자, 속성"
  - "참조, 공급자 속성"
  - "공급자 속성 참조"
ms.assetid: bfbb3851-5eed-467a-a179-4a97a9515525
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 공급자의 속성 참조
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

원하는 속성의 속성 그룹과 속성 ID를 찾습니다.  자세한 내용은 *OLE DB Programmer's Reference*의 [OLE DB Properties](https://msdn.microsoft.com/en-us/library/ms722734.aspx)를 참조하십시오.  
  
 다음 예제에서는 행 집합에서 속성을 가져온다고 가정합니다.  세션이나 명령을 사용하는 것에 대한 코드는 비슷하지만 서로 다른 인터페이스를 사용합니다.  
  
 속성 그룹을 생성자에 대한 매개 변수로 사용하여 [CDBPropSet](../../data/oledb/cdbpropset-class.md) 개체를 만듭니다.  예를 들면 다음과 같습니다.  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  
```  
  
 속성 ID와 속성에 할당할 값을 전달하여 [AddProperty](../../data/oledb/cdbpropset-addproperty.md)를 호출합니다.  값 형식은 사용하는 속성에 따라 다릅니다.  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  
propset.AddProperty(DBPROP_IRowsetChange, true);  
propset.AddProperty(DBPROP_UPDATABILITY,  
DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_DELETE);  
```  
  
 `IRowset` 인터페이스를 사용하여 **GetProperties**를 호출하고  속성 집합을 매개 변수로 전달합니다.  다음은 최종 코드입니다.  
  
```  
CAgentRowset<CMyProviderCommand>* pRowset = (CAgentRowset<CMyProviderCommand>*) pThis;  
  
CComQIPtr<IRowsetInfo, &IID_IRowsetInfo> spRowsetProps = pRowset;  
  
DBPROPIDSET set;  
set.AddPropertyID(DBPROP_BOOKMARKS);  
DBPROPSET* pPropSet = NULL;  
ULONG ulPropSet = 0;  
HRESULT hr;  
  
if (spRowsetProps)  
   hr = spRowsetProps->GetProperties(1, &set, &ulPropSet, &pPropSet);  
  
if (pPropSet)  
{  
   CComVariant var = pPropSet->rgProperties[0].vValue;  
   CoTaskMemFree(pPropSet->rgProperties);  
   CoTaskMemFree(pPropSet);  
  
   if (SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE))  
   {  
      ...  // Use property here  
   }  
}  
```  
  
## 참고 항목  
 [OLE DB 공급자 템플릿을 사용하여 작업](../../data/oledb/working-with-ole-db-provider-templates.md)