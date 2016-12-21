---
title: "런타임 라이브러리 동작 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_DllMainCRTStartup"
  - "CRT_INIT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CRT_INIT 매크로"
  - "_DllMainCRTStartup 메서드"
  - "DllMain 함수"
  - "DLL[C++], 진입점 함수"
  - "DLL[C++], 런타임 라이브러리 동작"
  - "DLL[C++], 시작 시퀀스"
  - "프로세스 연결[C++]"
  - "프로세스 분리[C++]"
  - "런타임[C++], DLL 시작 시퀀스"
ms.assetid: e06f24ab-6ca5-44ef-9857-aed0c6f049f2
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 런타임 라이브러리 동작
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\/C\+\+ 런타임 라이브러리 코드는 DLL 시작 시퀀스를 수행하므로 Windows 3.x에서처럼 별도의 모듈과 링크해야 할 필요가 없습니다.  C\/C\+\+ 런타임 라이브러리 코드에는 **\_DllMainCRTStartup**이라는 DLL 진입점 함수가 포함되어 있습니다.  **\_DllMainCRTStartup** 함수는 C\/C\+\+ 런타임 라이브러리를 초기화하고 정적인 비지역 변수에 대해 C\+\+ 생성자를 호출하는 **\_CRT\_INIT** 호출 등을 포함하여 몇 가지 작업을 수행합니다.  이 함수가 없으면 런타임 라이브러리가 초기화되지 않은 상태로 남아 있게 됩니다.  **\_CRT\_INIT**는 정적으로 링크되는 CRT의 경우 또는 사용자 DLL에서 CRT DLL인 Msvcr90.dll에 링크하는 경우에 모두 사용할 수 있습니다.  
  
 링커 옵션인 \/ENTRY를 사용하여 다른 진입점 함수를 지정할 수는 있지만, 이 경우 진입점 함수가 **\_DllMainCRTStartup**이 수행하는 모든 작업을 중복 수행해야 하므로 다른 진입점 함수를 지정하지 않는 것이 좋습니다.  Visual C\+\+에서 DLL을 빌드할 때에는 자동으로 **\_DllMainCRTStartup**이 링크되므로 링커 옵션인 \/ENTRY를 사용하여 진입점 함수를 지정할 필요가 없습니다.  
  
 **\_DllMainCRTStartup**은 C 런타임 라이브러리를 초기화할 뿐만 아니라 `DllMain`이라는 함수를 호출하기도 합니다.  Visual C\+\+에서는 빌드하는 DLL의 종류에 따라 자동으로 `DllMain`이 제공되고 링크되므로 **\_DllMainCRTStartup**에 호출할 항목이 항상 포함됩니다.  이러한 방식으로 DLL을 초기화할 필요가 없는 경우에는 DLL을 빌드할 때 별도의 작업을 수행하지 않아도 됩니다.  DLL을 초기화해야 하는 경우, 코드를 추가하는 위치는 작성하는 DLL의 종류에 따라 다릅니다.  자세한 내용은 [DLL 초기화](../build/initializing-a-dll.md)를 참조하십시오.  
  
 C\/C\+\+ 런타임 라이브러리 코드는 정적인 비지역 변수에 대한 생성자 및 소멸자를 호출합니다.  예를 들어 다음의 DLL 소스 코드에서 `Equus` 및 `Sugar`는 Horses.h에 정의된 `CHorse` 클래스의 정적인 비 로컬 개체입니다.  이 개체는 함수의 외부에서 정의되기 때문에 `CHorse`의 생성자 함수나 소멸자 함수를 호출하는 함수가 소스 코드에 포함되어 있지 않습니다.  따라서 해당 생성자 및 소멸자는 런타임 코드에서 호출되어야 합니다.  응용 프로그램의 런타임 라이브러리 코드에서도 이 함수를 호출할 수 있습니다.  
  
```  
#include "horses.h"  
  
CHorse  Equus( ARABIAN, MALE );  
CHorse  Sugar( THOROUGHBRED, FEMALE );  
  
BOOL    WINAPI   DllMain (HANDLE hInst,   
                            ULONG ul_reason_for_call,  
                            LPVOID lpReserved)  
...  
```  
  
 새 프로세스가 DLL을 사용하려고 할 때마다 운영 체제에서는 해당 DLL의 데이터에 대한 별도의 복사본을 만듭니다. 이를 프로세스 연결이라고 합니다.  해당 DLL에 대한 런타임 라이브러리 코드는 모든 전역 개체에 대한 생성자를 호출한 다음 프로세스 연결이 선택된 상태에서 `DllMain` 함수를 호출합니다.  이와 반대의 경우는 프로세스 분리라고 합니다. 이 경우 런타임 라이브러리 코드는 프로세스 분리가 선택된 상태에서 `DllMain`을 호출한 다음 `atexit` 함수 등의 종료 함수 목록, 전역 개체에 대한 소멸자 및 정적 개체에 대한 소멸자를 호출합니다.  프로세스 연결의 이벤트 순서는 프로세스 분리의 이벤트 순서와 반대입니다.  
  
 스레드를 연결하거나 분리할 때에도 런타임 라이브러리 코드가 호출되지만 이 경우에는 런타임 라이브러리가 직접 초기화 및 종료를 수행하지 않습니다.  
  
## 수행할 작업  
  
-   [DLL 초기화](../build/initializing-a-dll.md)  
  
## 참고 항목  
 [Visual C\+\+의 DLL](../build/dlls-in-visual-cpp.md)