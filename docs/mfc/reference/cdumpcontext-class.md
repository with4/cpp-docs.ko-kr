---
title: "CDumpContext Class | Microsoft Docs"
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
  - "CDumpContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AfxDump object"
  - "CDumpContext class"
  - "진단, diagnostic classes"
  - "diagnostic classes"
  - "진단, diagnostic classes"
ms.assetid: 98c52b2d-14b5-48ed-b423-479a4d1c60fa
caps.latest.revision: 20
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDumpContext Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스트림 지향 지원 진단 출력 형태의 읽을 텍스트입니다.  
  
## 구문  
  
```  
class CDumpContext  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDumpContext::CDumpContext](../Topic/CDumpContext::CDumpContext.md)|`CDumpContext` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDumpContext::DumpAsHex](../Topic/CDumpContext::DumpAsHex.md)|표시 된 항목의 16 진수 형식으로 덤프합니다.|  
|[CDumpContext::Flush](../Topic/CDumpContext::Flush.md)|덤프 컨텍스트 버퍼에 데이터를 플러시합니다.|  
|[CDumpContext::GetDepth](../Topic/CDumpContext::GetDepth.md)|덤프의 깊이에 해당 하는 정수를 가져옵니다.|  
|[CDumpContext::HexDump](../Topic/CDumpContext::HexDump.md)|16 진수 형식에서 배열에 포함 된 바이트를 덤프 합니다.|  
|[CDumpContext::SetDepth](../Topic/CDumpContext::SetDepth.md)|덤프의 깊이 설정 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CDumpContext::operator \<\<](../Topic/CDumpContext::operator%20%3C%3C.md)|변수 및 개체 덤프 컨텍스트에 삽입합니다.|  
  
## 설명  
 `CDumpContext`기본 클래스에 없는 것입니다.  
  
 사용할 수 있는  [afxDump](../Topic/afxDump%20\(CDumpContext%20in%20MFC\).md), predeclared는 `CDumpContext` 개체를 덤프 하는 대부분의.  `afxDump` 개체는 Mfc 라이브러리의 디버그 버전 에서만 사용할 수 있습니다.  
  
 일부의 메모리  [진단 서비스](../../mfc/reference/diagnostic-services.md) 사용 `afxDump` 해당 출력에 대 한.  
  
 Windows 환경에서 출력은 미리 정의 된 `afxDump` 개체, 개념적으로 `cerr` 스트림, 디버거는 Windows 함수를 통해 라우트됩니다  **OutputDebugString**.  
  
 `CDumpContext` 클래스에는 오버 로드 된 삽입 \(**\<\<**\) 연산자에 대 한 `CObject` 포인터는 개체의 데이터를 덤프 합니다.  사용자 지정 덤프 형식 파생된 개체에 대해 필요한 경우 재정의  [CObject::Dump](../Topic/CObject::Dump.md).  대부분의 Microsoft Foundation 클래스는 재정의 된 구현 `Dump` 멤버 함수입니다.  
  
 클래스에서 파생 된 `CObject`, 같은 `CString`, `CTime`, 및 `CTimeSpan`, 자신의 오버 로드 된 `CDumpContext` 삽입 연산자를 자주 사용 하지 구조  **CFileStatus**, `CPoint`, 및 `CRect`.  
  
 사용 하는 경우는  [클래스](../Topic/IMPLEMENT_DYNAMIC.md) 또는  [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md) 매크로 해당 클래스의 구현에서 `CObject::Dump` 이름을 인쇄를 `CObject`\-파생 클래스.  그렇지 않으면 인쇄 될 `CObject`.  
  
 `CDumpContext` 클래스 라이브러리는 디버그 및 릴리스 버전에 사용할 수 있지만 `Dump` 멤버 함수는 디버그 버전에만 정의 됩니다.  사용  **\# ifdef \_DEBUG** \/ `#endif` 진단 코드, 사용자 지정을 포함 하도록 문 `Dump` 멤버 함수입니다.  
  
 직접 만들기 전에 `CDumpContext` 개체를 만들어야는 `CFile` 덤프 대상으로 사용 되는 개체입니다.  
  
 에 대 한 자세한 내용은 `CDumpContext`를 참조 하십시오  [MFC 응용 프로그램 디버깅](../Topic/MFC%20Debugging%20Techniques.md).  
  
 **\# define \_DEBUG**  
  
## 상속 계층 구조  
 `CDumpContext`  
  
## 요구 사항  
 **헤더:**  afx.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)