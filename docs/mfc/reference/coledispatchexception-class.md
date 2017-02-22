---
title: "COleDispatchException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDispatchException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "자동화, 예외"
  - "COleDispatchException class"
  - "예외, OLE"
  - "OLE exceptions, to IDispatch interface"
ms.assetid: 0e95c8be-e21a-490c-99ec-181c6a9a26d0
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleDispatchException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE에 특정 예외 처리 `IDispatch` 인터페이스는 OLE 자동화의 핵심 부분입니다.  
  
## 구문  
  
```  
class COleDispatchException : public CException  
```  
  
## 멤버  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[COleDispatchException::m\_dwHelpContext](../Topic/COleDispatchException::m_dwHelpContext.md)|오류에 대 한 도움말 컨텍스트입니다.|  
|[COleDispatchException::m\_strDescription](../Topic/COleDispatchException::m_strDescription.md)|구두 오류 설명입니다.|  
|[COleDispatchException::m\_strHelpFile](../Topic/COleDispatchException::m_strHelpFile.md)|도움말 파일 사용 `m_dwHelpContext`.|  
|[COleDispatchException::m\_strSource](../Topic/COleDispatchException::m_strSource.md)|응용 프로그램 예외를 생성 합니다.|  
|[COleDispatchException::m\_wCode](../Topic/COleDispatchException::m_wCode.md)|`IDispatch`\-특정 오류 코드입니다.|  
  
## 설명  
 예외 클래스에서 파생 된 것은 `CException` 기본 클래스를 `COleDispatchException` 사용할 수 있습니다는  **THROW**, `THROW_LAST`,  **시도**,  **CATCH**, `AND_CATCH`, 및 `END_CATCH` 매크로.  
  
 일반적으로 호출 해야  [AfxThrowOleDispatchException](../Topic/AfxThrowOleDispatchException.md) 를 만들고 throw 하는 `COleDispatchException` 개체입니다.  
  
 예외에 대 한 자세한 내용은 문서를 참조 하십시오.  [예외 처리 \(MFC\)](../../mfc/exception-handling-in-mfc.md) 및  [예외: OLE 예외](../../mfc/exceptions-ole-exceptions.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [넓습니다](../../mfc/reference/cexception-class.md)  
  
 `COleDispatchException`  
  
## 요구 사항  
 **헤더:**  afxdisp.h  
  
## 참고 항목  
 [CALCDRIV MFC 샘플](../../top/visual-cpp-samples.md)   
 [CException Class](../../mfc/reference/cexception-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDispatchDriver Class](../../mfc/reference/coledispatchdriver-class.md)   
 [COleException Class](../../mfc/reference/coleexception-class.md)