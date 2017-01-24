---
title: "방법: 등록이 필요 없는 COM 구성 요소 빌드 | Microsoft Docs"
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
  - "COM 구성 요소, 등록 필요 없음"
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 방법: 등록이 필요 없는 COM 구성 요소 빌드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

등록이 필요 없는 COM 구성 요소란 DLL에 매니페스트가 빌드되어 있는 COM 구성 요소를 말합니다.  
  
### COM 구성 요소에 매니페스트를 빌드하려면  
  
1.  COM 구성 요소에 대한 프로젝트 속성 페이지를 엽니다.  
  
2.  **구성 속성** 노드를 확장한 다음 **매니페스트 도구** 노드를 확장합니다.  
  
3.  **입력 및 출력** 속성 페이지를 선택한 다음 **매니페스트 포함** 속성을 **예**로 설정합니다.  
  
4.  **확인**을 클릭합니다.  
  
5.  솔루션을 빌드합니다.  
  
## 참고 항목  
 [격리된 응용 프로그램](http://msdn.microsoft.com/library/aa375190)   
 [Side\-by\-side 어셈블리](_win32_side_by_side_assemblies)   
 [방법: COM 구성 요소를 사용하는 격리된 응용 프로그램 빌드](../build/how-to-build-isolated-applications-to-consume-com-components.md)