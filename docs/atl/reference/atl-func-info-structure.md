---
title: "_ATL_FUNC_INFO Structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ATL_FUNC_INFO"
  - "ATL::_ATL_FUNC_INFO"
  - "ATL._ATL_FUNC_INFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_FUNC_INFO structure"
  - "ATL_FUNC_INFO structure"
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _ATL_FUNC_INFO Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dispinterface에서 메서드나 속성에 설명 하는 데 사용 되는 형식 정보를 포함 합니다.  
  
## 구문  
  
```  
  
      struct _ATL_FUNC_INFO{  
   CALLCONV cc;  
   VARTYPE vtReturn;  
   SHORT nParams;  
   VARTYPE pVarTypes[_ATL_MAX_VARTYPES];  
};  
```  
  
## Members  
 **참조**  
 호출 규칙  이 구조를 사용 하는 경우는  [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) 클래스에서이 멤버 여야  **CC\_STDCALL**.  `CC_CDECL`Windows CE 지원 되는 옵션만 `CALLCONV` 필드는 `_ATL_FUNC_INFO` 구조.  다른 값은 지원 되지 않는 따라서 동작이 정의 되지 않았습니다.  
  
 **vtReturn**  
 Variant 형식 함수 값을 반환 합니다.  
  
 **nParams**  
 함수 매개 변수 개수입니다.  
  
 **pVarTypes**  
 함수 매개 변수를 variant 형식의 배열입니다.  
  
## 설명  
 내부적으로 ATL이이 구조를 사용 하 여 형식 라이브러리에서 얻은 정보를 보관 합니다.  이벤트 처리기 사용에 대 한 형식 정보를 제공 하는 경우이 구조를 직접 조작할 필요가 있는  [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) 클래스 및  [SINK\_ENTRY\_INFO](../Topic/SINK_ENTRY_INFO.md) 매크로.  
  
## 예제  
 Dispinterface 메서드에 IDL에 정의 된 제공:  
  
 [!code-cpp[NVC_ATL_Windowing#139](../../atl/codesnippet/CPP/atl-func-info-structure_1.idl)]  
  
 정의 하는 `_ATL_FUNC_INFO` 구조.  
  
 [!code-cpp[NVC_ATL_Windowing#140](../../atl/codesnippet/CPP/atl-func-info-structure_2.h)]  
  
## 요구 사항  
 **헤더:** atlcom.h  
  
## 참고 항목  
 [구조체](../../atl/reference/atl-structures.md)   
 [IDispEventSimpleImpl Class](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK\_ENTRY\_INFO](../Topic/SINK_ENTRY_INFO.md)