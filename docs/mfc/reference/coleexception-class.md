---
title: "COleException Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleException class"
  - "예외, OLE"
ms.assetid: 2571e9fe-26cc-42f0-9ad9-8ad5b4311ec1
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE 작업에 관련 된 예외 조건을 나타냅니다.  
  
## 구문  
  
```  
class COleException : public CException  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleException::Process](../Topic/COleException::Process.md)|Catch 된 예외에는 OLE 반환 코드를 변환합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[COleException::m\_sc](../Topic/COleException::m_sc.md)|예외에 대 한 이유를 나타내는 상태 코드가 포함 됩니다.|  
  
## 설명  
 `COleException` 클래스 예외에 대 한 이유를 나타내는 상태 코드를 포함 하는 공용 데이터 멤버를 포함 합니다.  
  
 일반적으로 만들지 해야는 `COleException` 개체를 직접. 대신 호출 해야  [AfxThrowOleException](../Topic/AfxThrowOleException.md).  
  
 예외에 대 한 자세한 내용은 문서를 참조 하십시오.  [예외 처리 \(MFC\)](../../mfc/exception-handling-in-mfc.md) 및  [예외: OLE 예외](../../mfc/exceptions-ole-exceptions.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [넓습니다](../../mfc/reference/cexception-class.md)  
  
 `COleException`  
  
## 요구 사항  
 **헤더:**  afxdisp.h  
  
## 참고 항목  
 [CALCDRIV MFC 샘플](../../top/visual-cpp-samples.md)   
 [CException Class](../../mfc/reference/cexception-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)