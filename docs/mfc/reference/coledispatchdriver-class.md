---
title: "COleDispatchDriver Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDispatchDriver"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Automation clients, implementing Automation"
  - "COleDispatchDriver class"
  - "OLE dispatch interface"
ms.assetid: 3ed98daf-cdc7-4374-8a0c-cf695a8d3657
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# COleDispatchDriver Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

클라이언트 쪽 OLE 자동화를 구현합니다.  
  
## 구문  
  
```  
class COleDispatchDriver  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleDispatchDriver::COleDispatchDriver](../Topic/COleDispatchDriver::COleDispatchDriver.md)|`COleDispatchDriver` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleDispatchDriver::AttachDispatch](../Topic/COleDispatchDriver::AttachDispatch.md)|첨부는 `IDispatch` 연결 하는 `COleDispatchDriver` 개체입니다.|  
|[COleDispatchDriver::CreateDispatch](../Topic/COleDispatchDriver::CreateDispatch.md)|생성 된 `IDispatch` 연결을 연결 하 고는 `COleDispatchDriver` 개체.|  
|[COleDispatchDriver::DetachDispatch](../Topic/COleDispatchDriver::DetachDispatch.md)|분리 된 `IDispatch` 를 해제 하지 않고 연결 합니다.|  
|[COleDispatchDriver::GetProperty](../Topic/COleDispatchDriver::GetProperty.md)|자동화 속성을 가져옵니다.|  
|[COleDispatchDriver::InvokeHelper](../Topic/COleDispatchDriver::InvokeHelper.md)|자동화 메서드를 호출 하는 도우미입니다.|  
|[COleDispatchDriver::ReleaseDispatch](../Topic/COleDispatchDriver::ReleaseDispatch.md)|릴리스는 `IDispatch` 연결 합니다.|  
|[COleDispatchDriver::SetProperty](../Topic/COleDispatchDriver::SetProperty.md)|자동화 속성을 설정합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[COleDispatchDriver::operator \=](../Topic/COleDispatchDriver::operator%20=.md)|복사 원본 값으로는 `COleDispatchDriver` 개체입니다.|  
|[COleDispatchDriver::operator LPDISPATCH](../Topic/COleDispatchDriver::operator%20LPDISPATCH.md)|액세스 하는 기본 `IDispatch` 포인터.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[COleDispatchDriver::m\_bAutoRelease](../Topic/COleDispatchDriver::m_bAutoRelease.md)|릴리스할 지 여부를 지정 하는 `IDispatch` 중 `ReleaseDispatch` 또는 개체 소멸.|  
|[COleDispatchDriver::m\_lpDispatch](../Topic/COleDispatchDriver::m_lpDispatch.md)|포인터를 나타냅니다의 `IDispatch` 인터페이스를 연결 하려면 `COleDispatchDriver`.|  
  
## 설명  
 `COleDispatchDriver`기본 클래스에 없는 것입니다.  
  
 OLE 디스패치 인터페이스 개체의 메서드 및 속성에 대 한 액세스를 제공합니다.  멤버 함수를 `COleDispatchDriver` 연결, 분리, 작성 및 유형의 디스패치 연결 해제 `IDispatch`.  가변 인수 목록을 다른 멤버 함수를 사용 하 여 호출을 간단 하 게  **IDispatch::Invoke**.  
  
 이 클래스를 직접 사용할 수 있지만 클래스 추가 마법사에서 만든 클래스는 일반적으로 사용 됩니다.  형식 라이브러리를 가져와서 새 C\+\+ 클래스를 만들 때 새 클래스에서 파생 된 `COleDispatchDriver`.  
  
 사용에 대 한 자세한 내용은 `COleDispatchDriver`, 다음 문서를 참조 하십시오.  
  
-   [자동화 클라이언트](../../mfc/automation-clients.md)  
  
-   [자동화 서버](../../mfc/automation-servers.md)  
  
## 상속 계층 구조  
 `COleDispatchDriver`  
  
## 요구 사항  
 **헤더:**  afxdisp.h  
  
## 참고 항목  
 [MFC 샘플 CALCDRIV](../../top/visual-cpp-samples.md)   
 [MFC ACDUAL 샘플](../../top/visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)