---
title: "OLE 백그라운드: MFC 구현 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IMarshall"
  - "IMoniker"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IMarshall 클래스"
  - "IMoniker 인터페이스, MFC"
  - "MFC 라이브러리, 구현"
  - "OLE IMarshal 인터페이스"
  - "OLE IMoniker 인터페이스"
  - "OLE IUnknown"
  - "OLE MFC 라이브러리 구현"
  - "OLE, 복합 파일"
ms.assetid: 2b67016a-d78e-4d60-925f-c28ec8fb6180
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# OLE 백그라운드: MFC 구현
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

OLE API의 크기와 복잡성으로 인해 OLE 응용 프로그램을 직접 작성하기 위해 호출하는데 매우 시간이 오래 걸릴 수 있습니다.  OLE의 Microsoft Foundation Class 라이브러리 구현의 목표는 완벽한 기능을 갖춘 OLE 지원 응용 프로그램을 만들기 위해해야 할 일의 양을 줄이는 것입니다.  
  
 이 문서에서는 MFC 내부에서 구현되지 않은 OLE API 부분을 설명합니다.  토론은 [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]의 OLE 단원에 무엇이 맵을 어떻게 구현하는지에 대해 설명합니다.  
  
##  <a name="_core_portions_of_ole_not_implemented_by_the_class_library"></a> 클래스 라이브러리에서 구현되지 않은 OLE 부분  
 몇 가지 인터페이스와 기능은 OLE MFC에서 직접 지원하지 않습니다.  이러한 기능을 사용하려면 OLE API를 직접 호출할 수 있습니다.  
  
 IMoniker 인터페이스  
 `IMoniker`  인터페이스는 클래스 라이브러리에서 구현 됩니다 \(예를 들어,  `COleServerItem`  클래스\) 그러나 프로그래머에게 노출되지는 않습니다.  이 인터페이스에 대한 자세한 내용은   [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] OLE 섹션의 OLE 모니커 구현을 참조하십시오.  그러나 [CMonikerFile](../mfc/reference/cmonikerfile-class.md) 및  [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) 클래스 또한 참고하십시오.  
  
 IUnknown 및 IMarshal 인터페이스  
 **IUnknown** 인터페이스는 클래스 라이브러리에서 구현 되지만 프로그래머에게 노출되지 않습니다.   **IMarshal** 인터페이스 클래스 라이브러리에서 구현 되지 않지만 내부적으로 사용됩니다.  클래스 라이브러리를 사용한 자동화 서버 빌드는 이미 마샬링 기능이 내장 되어 있습니다.  
  
 Docfiles \(복합 파일\)  
 복합 파일은 클래스 라이브러리에서 부분적으로 지원됩니다.  직접 만드는 것을 넘어 복합 파일을 조작 하는 함수는 지원하지 않습니다.  MFC는 **COleFileStream** 클래스를 사용하여  표준 파일 함수와 스트림 조작을 지원합니다.  자세한 내용은   [컨테이너: 복합 파일](../mfc/containers-compound-files.md)문서를 참조 하십시오..  
  
 In\-process 서버와 개체 처리기  
 프로세스에서 서버와 개체 처리기 시각적 데이터를 편집 또는 동적 연결 라이브러리 \(DLL\)의 모든 구성 요소 개체 모델 \(COM\) 개체의 구현을 허용합니다.  이렇게 하려면 OLE API를 직접 호출하여 DLL을 구현할 수 있습니다.  그러나, 사용자 인터페이스가 없는 자동화 서버를 작성하는 경우에는 해당 서버를 in\-process 서버로 만든 다음 DLL에 완전히 포함시킬 수 있습니다.  이러한 항목에 대한 자세한 내용은  [자동화 서버](../mfc/automation-servers.md)을 참조하십시오.  
  
> [!TIP]
>  자동화 서버를 구현 하는 가장 쉬운 방법은 DLL에 배치하는 것입니다.  MFC는 이 방법을 지원합니다.  
  
 Microsoft Foundation OLE 클래스 OLE 인터페이스를 구현 하는 방법에 대한 자세한 내용은  [38](../mfc/tn038-mfc-ole-iunknown-implementation.md),  [39](../mfc/tn039-mfc-ole-automation-implementation.md), 및  [40](../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md)의 MFC 기술 참고를 참조하십시오.  
  
## 참고 항목  
 [OLE 백그라운드](../mfc/ole-background.md)   
 [OLE 백그라운드 구현 전략](../mfc/ole-background-implementation-strategies.md)