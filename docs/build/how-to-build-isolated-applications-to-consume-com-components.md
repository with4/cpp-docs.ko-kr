---
title: "방법: COM 구성 요소를 사용하는 격리된 응용 프로그램 빌드 | Microsoft Docs"
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
  - "격리된 응용 프로그램[C++]"
ms.assetid: 04587547-1174-44ab-bd99-1292358fba20
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 방법: COM 구성 요소를 사용하는 격리된 응용 프로그램 빌드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

격리된 응용 프로그램이란 프로그램에 매니페스트가 빌드되어 있는 응용 프로그램을 말합니다.  격리된 응용 프로그램을 만들어 COM 구성 요소를 사용할 수 있습니다.  
  
### 격리된 응용 프로그램의 매니페스트에 COM 참조를 추가하려면  
  
1.  격리된 응용 프로그램에 대한 프로젝트 속성 페이지를 엽니다.  
  
2.  **구성 속성** 노드를 확장한 다음 **매니페스트 도구** 노드를 확장합니다.  
  
3.  **격리 COM** 속성 페이지를 선택한 다음 **구성 요소 파일 이름** 속성을 격리된 응용 프로그램이 사용할 COM 구성 요소 이름으로 설정합니다.  
  
4.  **확인**을 클릭합니다.  
  
### 격리된 응용 프로그램에 매니페스트를 빌드하려면  
  
1.  격리된 응용 프로그램에 대한 프로젝트 속성 페이지를 엽니다.  
  
2.  **구성 속성** 노드를 확장한 다음 **매니페스트 도구** 노드를 확장합니다.  
  
3.  **입력 및 출력** 속성 페이지를 선택한 다음 **매니페스트 포함** 속성을 **예**로 설정합니다.  
  
4.  **확인**을 클릭합니다.  
  
5.  솔루션을 빌드합니다.  
  
## 참고 항목  
 [격리된 응용 프로그램](http://msdn.microsoft.com/library/aa375190)   
 [Side\-by\-side 어셈블리](_win32_side_by_side_assemblies)