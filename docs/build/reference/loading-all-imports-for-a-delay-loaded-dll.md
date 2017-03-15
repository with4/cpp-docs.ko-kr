---
title: "지연 로드된 DLL에 대한 모든 가져오기 로드 | Microsoft Docs"
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
  - "__HrLoadAllImportsForDll 링커 옵션"
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 지연 로드된 DLL에 대한 모든 가져오기 로드
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

delayhlp.cpp에 정의된 **\_\_HrLoadAllImportsForDll** 함수를 사용하면 링커에서는 [\/DELAYLOAD](../../build/reference/delayload-delay-load-import.md) 링커 옵션을 사용하여 지정된 DLL에서 가져오기를 모두 로드합니다.  
  
 가져오기를 모두 로드하면 코드의 한 지점에서 오류 처리를 수행할 수 있으며 가져오기를 실제로 호출할 때 예외 처리를 사용할 필요가 없습니다.  또한 도우미 코드에서 가져오기를 로드하지 못할 때 응용 프로그램의 프로세스가 부분적으로 실패하는 경우도 발생하지 않습니다.  
  
 **\_\_HrLoadAllImportsForDll**을 호출해도 후크 및 오류 처리의 동작은 바뀌지 않습니다. 자세한 내용은 [오류 처리 및 알림](../../build/reference/error-handling-and-notification.md)을 참조하십시오.  
  
 **\_\_HrLoadAllImportsForDll**에 전달된 DLL 이름은 자체 DLL 내부에 저장되는 이름과 비교되며 대\/소문자를 구분합니다.  
  
 다음 예제에서는 **\_\_HrLoadAllImportsForDll**을 호출하는 방법을 보여 줍니다.  
  
```  
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {  
   printf ( "failed on snap load, exiting\n" );  
   exit(2);  
}  
```  
  
## 참고 항목  
 [링커의 지연 로드된 DLL 지원](../../build/reference/linker-support-for-delay-loaded-dlls.md)