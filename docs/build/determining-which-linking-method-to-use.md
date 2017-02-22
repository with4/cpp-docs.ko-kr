---
title: "사용할 링크 방법 결정 | Microsoft Docs"
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
  - "명시적 링크[C++]"
  - "암시적 링크[C++]"
ms.assetid: 6b6d3fec-4711-4a30-af5b-354b965ecaec
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 사용할 링크 방법 결정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

링크에는 암시적 링크와 명시적 링크라는 두 가지 형식이 있습니다.  
  
## 암시적 링크  
 [암시적 링크](../build/linking-implicitly.md)는 응용 프로그램 코드에서 내보낸 DLL 함수를 호출할 때 발생합니다.  실행 파일을 호출하는 소스 코드가 컴파일되거나 어셈블되면 DLL 함수가 호출되어 개체 코드에 외부 함수 참조를 생성시킵니다.  이 외부 참조를 확인하려면 해당 응용 프로그램은 DLL 작성자가 제공하는 가져오기 라이브러리\(.lib 파일\)에 링크해야 합니다.  
  
 가져오기 라이브러리에는 DLL을 로드하고 DLL에 있는 함수를 호출하기 위한 코드만 들어 있습니다.  가져오기 라이브러리에 외부 함수가 있으면 해당 함수의 코드가 DLL에 있다는 사실이 링커에 전달됩니다.  DLL에 대한 외부 참조를 확인하려면 프로세스 시작 시 DLL 코드가 있는 위치를 시스템에 알려주는 정보를 링커에서 실행 파일에 추가하기만 하면 됩니다.  
  
 시스템은 동적으로 링크된 참조가 있는 프로그램을 시작할 때 프로그램의 실행 파일에 있는 이 정보를 사용하여 필요한 DLL을 찾습니다.  해당 DLL을 찾을 수 없으면 시스템에서 프로세스를 종료하고 오류를 알리는 대화 상자를 표시합니다.  그렇지 않으면 시스템에서 해당 DLL 모듈을 프로세스의 주소 공간에 매핑합니다.  
  
 임의의 DLL에 초기화 및 종료 코드에 대한 진입점 함수가 포함된 경우 운영 체제에서 해당 함수를 호출합니다.  진입점 함수에 전달되는 매개 변수 중 하나는 해당 DLL이 해당 프로세스에 연결됨을 나타내는 코드를 지정합니다.  진입점 함수가 TRUE를 반환하지 않으면 시스템에서 프로세스를 종료하고 오류를 보고합니다.  
  
 마지막으로 시스템에서 프로세스의 실행 코드를 수정하여 해당 DLL 함수의 시작 주소를 제공합니다.  
  
 프로그램의 다른 모든 코드와 마찬가지로 DLL 코드도 프로세스 시작 시 해당 프로세스의 주소 공간에 매핑되며 필요할 때만 메모리 안으로 로드됩니다.  따라서, 이전 버전의 Windows에서 로드 방식을 제어하기 위해 .def 파일에서 사용한 **PRELOAD** 및 **LOADONCALL** 코드 특성은 필요하지 않습니다.  
  
## 명시적 링크  
 암시적 링크는 가장 사용하기 쉬운 링크 방법이므로 대부분의 응용 프로그램에서 사용됩니다.  그러나 [명시적 링크](../build/linking-explicitly.md)를 사용해야 하는 경우도 있습니다.  다음은 명시적 링크를 사용해야 하는 몇 가지 일반적인 이유입니다.  
  
-   응용 프로그램은 런타임까지 해당 응용 프로그램이 로드해야 할 DLL의 이름을 모릅니다.  예를 들어, 응용 프로그램은 구성 파일에서 DLL 및 내보내기 함수의 이름을 가져와야 합니다.  
  
-   암시적 링크를 사용하는 프로세스는 프로세스 시작 시 해당 DLL이 없으면 운영 체제에 의해 자동으로 종료됩니다.  반면, 명시적 링크를 사용하는 프로세스는 이러한 경우에 종료되지 않고 오류 복구를 시도할 수 있습니다.  예를 들어, 프로세스는 사용자에게 오류를 알려 사용자가 다른 DLL 경로를 지정하도록 할 수 있습니다.  
  
-   또한 암시적 링크를 사용하는 프로세스는 해당 프로세스가 링크되는 DLL 중 어느 하나의 `DllMain` 함수에 오류가 발생하는 경우에도 자동으로 종료됩니다.  반면, 명시적 링크를 사용하는 프로세스는 이 경우에도 종료되지 않습니다.  
  
-   여러 DLL에 암시적으로 링크하는 응용 프로그램의 경우에는 응용 프로그램이 로드될 때 Windows에서 해당 DLL을 모두 자동으로 로드하므로 프로그램의 시작 속도가 느릴 수 있습니다.  따라서 응용 프로그램이 로드 후 즉시 필요한 DLL에는 암시적으로 링크하고 다른 DLL에는 대기하다가 필요할 때 명시적으로 링크하면 프로그램의 시작 성능을 향상시킬 수 있습니다.  
  
-   명시적 링크를 사용하면 응용 프로그램을 가져오기 라이브러리에 링크하지 않아도 됩니다.  서수 값이 아니라 함수 이름을 사용하여 **GetProcAddress**를 호출하는 경우 DLL이 변경되어 내보내기 서수가 변경되면 명시적 링크를 사용하는 응용 프로그램은 다시 링크할 필요가 없지만, 암시적 링크를 사용하는 응용 프로그램은 새로운 가져오기 라이브러리에 다시 링크해야 합니다.  
  
 명시적 링크를 사용할 경우 다음과 같은 두 가지 문제가 발생할 수 있습니다.  
  
-   DLL에 `DllMain` 진입점 함수가 있는 경우, 운영 체제는 **LoadLibrary**를 호출한 스레드 컨텍스트에서 이 함수를 호출합니다.  그러나 이전에 **LoadLibrary**를 호출하고 이에 대응하는 **FreeLibrary** 함수를 호출하지 않아서 DLL이 이미 프로세스에 연결되어 있으면 진입점 함수는 호출되지 않습니다.  즉, 명시적 링크를 사용하면, **LoadLibrary** 또는 `AfxLoadLibrary`가 호출될 때 이미 있던 스레드는 초기화되지 않기 때문에 DLL이 `DllMain` 함수를 사용하여 프로세스의 각 스레드를 초기화하는 경우 문제가 생길 수 있습니다.  
  
-   DLL이 **\_\_declspec\(thread\)** 같은 정적 범위의 데이터를 선언하는 경우 명시적으로 링크하면 보호 오류가 발생할 수 있습니다.  **LoadLibrary**를 사용하여 DLL이 로드된 후 코드에서 이 데이터를 참조할 때마다 보호 오류가 발생합니다. 정적 범위 데이터에는 전역 및 지역 정적 항목이 포함됩니다. 따라서 DLL을 만들 때에는 스레드 로컬 저장소를 사용하지 않거나, 동적 로드를 시도할 때 발생할 수 있는 문제를 DLL 사용자에게 알려야 합니다.  
  
## 수행할 작업  
  
-   [암시적 링크](../build/linking-implicitly.md)  
  
-   [명시적 링크](../build/linking-explicitly.md)  
  
## 추가 정보  
  
-   [Windows에서 DLL을 찾는 데 사용되는 검색 경로](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
-   [LoadLibrary 및 AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
-   [FreeLibrary 및 AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)  
  
-   [\<caps:sentence id\="tgt47" sentenceid\="8081a197f9413cac12a30b57c2612af5" class\="tgtSentence"\>Using thread local storage in a dynamic\-link library\(Windows SDK\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms686997)  
  
## 참고 항목  
 [DLL에 실행 파일 링크](../build/linking-an-executable-to-a-dll.md)