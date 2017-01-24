---
title: "코드에는 문제가 없는 것 같으나 기본 DLL에 메모리 누수 문제가 있습니다. 메모리 누수를 찾으려면 어떻게 합니까? | Microsoft Docs"
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
  - "DLL[C++], 메모리 누수"
  - "메모리 누수[C++], DLL"
ms.assetid: a5d76573-b567-4b6a-8303-dafeeed9204d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 코드에는 문제가 없는 것 같으나 기본 DLL에 메모리 누수 문제가 있습니다. 메모리 누수를 찾으려면 어떻게 합니까?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

메모리 누수는 MFC가 메시지 처리기 함수 내에서 사용되는 임시 개체를 만들 때 발생할 수 있습니다.  기본 DLL에서는 MFC가 이러한 개체에 할당된 메모리를 자동으로 해제하지 않습니다.  자세한 내용은 [메모리 관리 및 디버그 힙](http://msdn.microsoft.com/ko-kr/34dc6ef6-31c9-460e-a2a7-15e7f8e3334b)이나 기술 자료 문서, "Cleaning Up Temporary MFC Objects in \_USRDLL DLLs"\(Q105286\)를 참조하십시오.  
  
 USRDLL이라는 용어는 Visual C\+\+ 설명서에서 더 이상 사용되지 않습니다.  정적으로 MFC에 링크한 기본 DLL의 특징은 이전 USRDLL의 특징과 같습니다.  기술 자료 문서에서 권장하는 사항은 동적으로 MFC에 링크되는 기본 DLL에도 적용됩니다.  즉, 위의 기술 자료 문서에 있는 정보는 정적으로 MFC에 링크하는 기본 DLL과 동적으로 MFC에 링크하는 기본 DLL 모두에 적용됩니다.  
  
## 참고 항목  
 [DLL 관련 질문과 대답](../build/dll-frequently-asked-questions.md)