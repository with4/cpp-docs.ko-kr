---
title: "연결 지점 구현 마법사 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.impl.cp.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "연결 지점 구현 마법사[C++]"
ms.assetid: c117f6c6-30f0-4adb-82b4-b1f34e0f0fa8
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 연결 지점 구현 마법사
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 마법사에서는 COM 개체에 대한 연결 지점을 구현합니다.  연결 가능 개체\(즉, 소스\)에서는 자체 인터페이스나 모든 보내기 인터페이스에 대한 연결 지점을 노출할 수 있습니다.  Visual C\+\+와 Windows에서는 보내기 인터페이스가 있는 형식 라이브러리를 제공합니다.  클라이언트에서는 개체\(즉, 싱크\)에 대해 각 보내기 인터페이스를 구현할 수 있습니다.  
  
 자세한 내용은 [ATL 연결 지점](../atl/atl-connection-points.md)을 참조하십시오.  
  
 **사용 가능한 형식 라이브러리**  
 연결 지점을 구현할 수 있는 인터페이스 정의가 포함된 사용 가능한 형식 라이브러리를 표시합니다.  사용할 형식 라이브러리가 포함된 파일을 찾으려면 줄임표\(...\) 단추를 클릭합니다.  
  
 **위치**  
 **사용 가능한 형식 라이브러리** 목록에서 현재 선택된 형식 라이브러리의 위치를 표시합니다.  
  
 **인터페이스**  
 **사용 가능한 형식 라이브러리** 상자에서 현재 선택된 형식 라이브러리에 해당 정의가 포함되어 있는 인터페이스를 표시합니다.  
  
|전송 단추|설명|  
|-----------|--------|  
|**\>**|**인터페이스** 목록에서 현재 선택된 인터페이스 이름을 **연결 지점 구현** 목록에 추가합니다.|  
|**\>\>**|**인터페이스** 목록에서 사용할 수 있는 모든 인터페이스 이름을 **연결 지점 구현** 목록에 추가합니다.|  
|**\<**|**연결 지점 구현** 목록에서 현재 선택된 인터페이스 이름을 제거합니다.|  
|**\<\<**|**연결 지점 구현** 목록에 현재 표시되어 있는 인터페이스 이름을 모두 제거합니다.|  
  
 **연결 지점 구현**  
 **마침**을 클릭할 때 해당 연결 지점을 구현하는 인터페이스 이름을 표시합니다.  
  
## 참고 항목  
 [연결 지점 구현](../ide/implementing-a-connection-point-visual-cpp.md)