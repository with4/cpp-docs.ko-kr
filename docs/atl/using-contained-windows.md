---
title: "Using Contained Windows | Microsoft Docs"
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
  - "ATL, windows"
  - "contained windows in ATL"
  - "windows [C++], ATL"
ms.assetid: 7b3d79e5-b569-413f-9b98-df4f14efbe2b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Using Contained Windows
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL에 포함 된 창으로 구현  [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md).  포함 된 창은 해당 메시지를 자체 클래스에서 처리 하지 않고 컨테이너 개체에 위임 하는 창을 나타냅니다.  
  
> [!NOTE]
>  클래스에서 파생 하지 않아도 `CContainedWindowT` 포함 된 windows를 사용 하려면.  
  
 포함 된 창으로 슈퍼는 기존 Windows 클래스 하거나 기존 창 서브 클래스는 있습니다.  기존 Windows는 해당 수퍼 클래스는 창을 만들 수 클래스, 생성자에 대 한 기존 클래스 이름을 먼저 지정 된 `CContainedWindowT` 개체입니다.  다음 호출 `CContainedWindowT::Create`.  Windows 클래스 이름을 지정할 필요가 기존 창을 서브 클래스 하 \(전달  **NULL** 생성자\).  호출 하면는 `CContainedWindowT::SubclassWindow` 메서드를 하위 클래스화 되는 창 핸들을 사용 합니다.  
  
 일반적으로 컨테이너 클래스의 데이터 멤버로 포함 된 windows를 사용합니다.  컨테이너 창이 될 필요는 없습니다. 하지만 파생 되어야  [CMessageMap](../atl/reference/cmessagemap-class.md).  
  
 포함 된 창은 대체 메시지 맵을 자체 메시지를 처리할 수 있습니다.  포함 된 창이 여러 개 있으면 여러 대체 포함 된 별도 창에 해당 메시지 맵을 선언 해야 합니다.  
  
## 예제  
 다음 두 개의 포함 된 창 가진 컨테이너 클래스의 예입니다.  
  
 [!code-cpp[NVC_ATL_Windowing#67](../atl/codesnippet/CPP/using-contained-windows_1.h)]  
  
 포함 된 창에 대 한 자세한 내용은  [SUBEDIT](../top/visual-cpp-samples.md) 샘플.  
  
## 참고 항목  
 [창 클래스](../atl/atl-window-classes.md)