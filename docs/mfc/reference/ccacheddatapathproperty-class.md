---
title: "CCachedDataPathProperty Class | Microsoft Docs"
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
  - "CCachedDataPathProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX 컨트롤[C++], 비동기"
  - "asynchronous controls [C++]"
  - "CCachedDataPathProperty class"
  - "memory files [C++]"
  - "OLE 컨트롤[C++], 비동기"
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCachedDataPathProperty Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구현 OLE 비동기적으로 전송 하 고 파일을 메모리에 캐시 된 속성을 제어 합니다.  
  
## 구문  
  
```  
class CCachedDataPathProperty : public CDataPathProperty  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CCachedDataPathProperty::CCachedDataPathProperty](../Topic/CCachedDataPathProperty::CCachedDataPathProperty.md)|`CCachedDataPathProperty` 개체를 생성합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CCachedDataPathProperty::m\_Cache](../Topic/CCachedDataPathProperty::m_Cache.md)|`CMemFile`데이터 캐시의 개체입니다.|  
  
## 설명  
 메모리 파일 디스크가 아닌 RAM에 저장 되 고 임시 빠른 전송에 유용 합니다.  
  
 함께  **CAysncMonikerFile** 및 `CDataPathProperty`, `CCachedDataPathProperty` OLE 컨트롤에 비동기 모니커를 사용 하는 기능을 제공 합니다.  와 `CCachedDataPathProperty` 개체를 통해 메모리 파일에 저장할 URL 또는 파일 원본에서 데이터를 비동기적으로 전송 하는 있는 `m_Cache` 공용 변수.  메모리 파일에서 모든 데이터를 저장 하 고 재정의 필요  [OnDataAvailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md) 에 대 한 알림을 보고 응답 하지 않는.  예를 들어, 대형 전송 하는 경우.GIF 파일을 컨트롤 자세한 데이터 도달 하 고 자체를 다시 그릴 것인지를 알리기 위해 무시 `OnDataAvailable` 알림을 확인 합니다.  
  
 클래스 `CCachedDataPathProperty` 에서 파생 된 `CDataPathProperty`.  
  
 인터넷 응용 프로그램에 비동기 모니커 및 ActiveX 컨트롤을 사용 하는 방법에 대 한 자세한 내용은 다음 항목을 참조 하십시오.  
  
-   [인터넷의 첫 번째 단계: ActiveX 컨트롤](../../mfc/activex-controls-on-the-internet.md)  
  
-   [인터넷의 첫 번째 단계: 비동기 모니커](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)  
  
 `CCachedDataPathProperty`  
  
## 요구 사항  
 **헤더:**  afxctl.h  
  
## 참고 항목  
 [CDataPathProperty Class](../../mfc/reference/cdatapathproperty-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDataPathProperty Class](../../mfc/reference/cdatapathproperty-class.md)