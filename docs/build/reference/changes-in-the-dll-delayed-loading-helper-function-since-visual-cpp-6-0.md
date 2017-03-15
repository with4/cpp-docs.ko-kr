---
title: "Visual C++ 6.0 이후 DLL 지연 로드 도우미 함수의 변경 내용 | Microsoft Docs"
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
  - "__delayLoadHelper2 함수"
  - "지연 DLL 로드, 변경 사항"
  - "도우미 함수, 변경 사항"
  - "PFromRva 메서드"
ms.assetid: 99f0be69-105d-49ba-8dd5-3be7939c0c72
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Visual C++ 6.0 이후 DLL 지연 로드 도우미 함수의 변경 내용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴퓨터에 여러 Visual C\+\+ 버전이 있거나 사용자가 직접 도우미 함수를 정의한 경우 DLL 지연 로드 도우미 함수가 변경되면 그 영향을 받을 수 있습니다.  예를 들면 다음과 같습니다.  
  
-   **\_\_delayLoadHelper**는 이제 **\_\_delayLoadHelper2**입니다.  
  
-   **\_\_pfnDliNotifyHook**는 이제 **\_\_pfnDliNotifyHook2**입니다.  
  
-   **\_\_pfnDliFailureHook**는 이제 **\_\_pfnDliFailureHook2**입니다.  
  
-   **\_\_FUnloadDelayLoadedDLL**은 이제 **\_\_FUnloadDelayLoadedDLL2**입니다.  
  
> [!NOTE]
>  기본 도우미 함수를 사용하는 경우 이러한 변경은 사용자에게 영향을 주지 않습니다.  링커를 호출하는 방법은 변경되지 않았습니다.  
  
## 여러 Visual C\+\+ 버전  
 컴퓨터에 여러 Visual C\+\+ 버전이 있는 경우 링커가 delayimp.lib와 일치하는지 확인해야 합니다.  일치하지 않는 경우 외부 기호를 확인할 수 없다는 `___delayLoadHelper2@8` 또는 `___delayLoadHelper@8` 링커 오류가 발생합니다.  전자는 새 링커가 이전 delayimp.lib를 사용한다는 의미이고 후자는 이전 링커가 새 delayimp.lib를 사용한다는 의미입니다.  
  
 확인할 수 없는 링커 오류가 발생한 경우 도우미 함수가 있을 것으로 예상되는 delayimp.lib에서 [dumpbin \/linkermember](../../build/reference/linkermember.md):1을 실행하여 대신 정의된 도우미 함수를 찾습니다.  도우미 함수가 개체 파일에 정의되어 있는 경우에는 [dumpbin \/symbols](../../build/reference/symbols.md)을 실행하여 `delayLoadHelper(2)`를 찾습니다.  
  
 Visual C\+\+ 6.0 링커가 있는 경우에는 다음과 같습니다.  
  
-   지연 로드 도우미의 .lib 또는 .obj 파일에서 dumpbin을 실행하여 **\_\_delayLoadHelper2**가 정의되어 있는지 확인합니다.  Visual C\+\+ 6.0 링커가 정의되지 않으면 링크는 수행되지 않습니다.  
  
-   지연 로드 도우미의 .lib 또는 .obj 파일에 **\_\_delayLoadHelper**를 정의합니다.  
  
## 사용자 정의 도우미 함수  
 사용자가 직접 도우미 함수를 정의하고 현재 버전의 Visual C\+\+를 사용하는 경우 다음을 수행합니다.  
  
-   도우미 함수의 이름을 **\_\_delayLoadHelper2**로 바꿉니다.  
  
-   지연 설명자\(delayimp.h의 ImgDelayDescr\)의 포인터가 32비트와 64비트 프로그램에서 모두 동작할 수 있도록 절대 주소\(VA\)에서 상대 주소\(RVA\)로 변경되었으므로 다시 포인터로 변환해야 합니다.  PFromRva 함수가 delayhlp.cpp에 새로 도입되었습니다.  설명자의 각 필드에서 이 함수를 사용하여 32비트나 64비트 포인터로 다시 변환할 수 있습니다.  기본 지연 로드 도우미 함수는 적절한 예제 템플릿으로 계속 사용될 수 있습니다.  
  
## 지연 로드된 DLL에 대한 모든 가져오기 로드  
 링커에서는 사용자가 지연 로드하도록 지정한 DLL에서 모든 가져오기를 로드할 수 있습니다.  자세한 내용은 [지연 로드된 DLL에 대한 모든 가져오기 로드](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md)를 참조하십시오.  
  
## 참고 항목  
 [Understanding the Helper Function](http://msdn.microsoft.com/ko-kr/6279c12c-d908-4967-b0b3-cabfc3e91d3d)