---
title: "Adding Functionality to the Composite Control | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX 컨트롤[C++], 이벤트"
  - "복합 컨트롤, 이벤트 처리"
  - "event handlers [C++], ActiveX 컨트롤"
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Adding Functionality to the Composite Control
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

합성 컨트롤에 필요한 컨트롤을 삽입 한 후 다음 단계 새 기능을 추가 해야 합니다.  이 새 기능에는 일반적으로 두 가지 범주로 나뉩니다.  
  
-   추가 인터페이스 지원 및 기능 추가, 특정 합성 컨트롤의 동작을 사용자 지정 합니다.  
  
-   포함 된 ActiveX 컨트롤 \(을\)에서 이벤트를 처리 합니다.  
  
 용도이 문서의 범위를이 섹션의 나머지 ActiveX 컨트롤에서 이벤트를 처리에 초점을 맞춥니다.  
  
> [!NOTE]
>  Windows 컨트롤에서 메시지를 처리 하는 경우를 참조 하십시오.  [창 구현](../atl/implementing-a-window.md) ATL에서 처리 된 메시지에 대 한 자세한 내용은  
  
 후에 ActiveX 컨트롤 삽입 대화 상자 리소스에 컨트롤을 마우스 오른쪽 단추로 클릭 하 고  **이벤트 처리기를 추가**.  처리 하 고 클릭 이벤트를 선택 합니다.  **추가 및 편집**.  이벤트 처리기 코드가 컨트롤의.h 파일에 추가 됩니다.  
  
 ActiveX 컨트롤을 합성 컨트롤에 대 한 연결 지점을 자동으로 연결 및 호출을 통해 연결이  [CComCompositeControl::AdviseSinkMap](../Topic/CComCompositeControl::AdviseSinkMap.md).  
  
## 참고 항목  
 [합성 컨트롤 기본 사항](../atl/atl-composite-control-fundamentals.md)