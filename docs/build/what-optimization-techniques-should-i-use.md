---
title: "로드 시 클라이언트 응용 프로그램의 성능을 향상시키려면 어떤 최적화 기술을 사용해야 합니까? | Microsoft Docs"
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
  - "DLL[C++], 최적화"
  - "최적화[C++], DLL"
  - "성능[C++], DLL"
ms.assetid: 2f8bbfb5-08b9-4a35-8302-25a1966881b1
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 로드 시 클라이언트 응용 프로그램의 성능을 향상시키려면 어떤 최적화 기술을 사용해야 합니까?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

정적으로 MFC에 링크한 기본 DLL을 동적으로 MFC에 링크한 기본 DLL로 변경하면 파일 크기가 작아집니다.  
  
 DLL에 내보낸 함수가 많으면 **\_\_declspec\(dllexport\)** 대신 .def 파일을 사용하여 함수를 내보내고 각 내보낸 함수에 .def 파일의 [NONAME 특성](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)을 사용합니다.  NONAME 특성을 사용하면 DLL의 내보내기 테이블에 서수 값만 저장되고 함수 이름은 저장되지 않으므로 파일 크기가 줄어듭니다.  
  
 응용 프로그램에 암시적으로 링크되는 DLL은 응용 프로그램이 로드될 때 로드됩니다.  따라서 로드 시 성능을 향상시키려면 DLL을 서로 다른 여러 개의 DLL로 나누는 것이 좋습니다.  즉, 호출 응용 프로그램에서 로드 후 즉시 필요한 모든 함수를 하나의 DLL에 포함시키고 호출 응용 프로그램이 해당 DLL에 암시적으로 링크하도록 합니다.  호출 응용 프로그램에서 즉시 필요하지는 않은 그 밖의 함수들은 다른 DLL에 포함시키고 응용 프로그램에서 해당 DLL에 명시적으로 링크하도록 합니다.  자세한 내용은 [사용할 링크 방법 결정](../build/determining-which-linking-method-to-use.md)을 참조하십시오.  
  
## 참고 항목  
 [DLL 관련 질문과 대답](../build/dll-frequently-asked-questions.md)