---
title: "CUtlProps::IsValidValue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CUtlProps::IsValidValue"
  - "CUtlProps.IsValidValue"
  - "IsValidValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsValidValue 메서드"
ms.assetid: 1164556e-8d98-429c-a396-fc9a699e0e97
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CUtlProps::IsValidValue
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

속성을 설정하기 전에 값의 유효성을 검사하는 데 사용됩니다.  
  
## 구문  
  
```  
  
      virtual HRESULT CUtlPropsBase::IsValidValue(  
   ULONG /* iCurSet */,  
   DBPROP* pDBProp   
);  
```  
  
#### 매개 변수  
 `iCurSet`  
 인덱스는 속성 집합 배열이 됩니다. 하나의 속성만이 설정된 경우 0입니다.  
  
 `pDBProp`  
 [DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx) 구조체의 새 값 및 속성 ID입니다.  
  
## 반환 값  
 표준 `HRESULT`입니다.  기본 반환 값은 `S_OK`입니다.  
  
## 설명  
 속성을 설정하기 위해서 값에 실행하고자 하는 유효성 검증 루틴이 있다면, 이 함수를 오버라이드해야 합니다  예를 들어, 유효한 값을 결정하는 암호 표와 대조적으로, **DBPROP\_AUTH\_PASSWORD**의 유효성을 검사할 수 있습니다.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [CUtlProps 클래스](../../data/oledb/cutlprops-class.md)