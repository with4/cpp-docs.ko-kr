---
title: "__declspec(dllimport)을 사용하여 응용 프로그램으로 가져오기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__declspec"
  - "dllimport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec(dllimport) 키워드[C++]"
  - "importing DLL[C++], __declspec(dllimport)"
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# __declspec(dllimport)을 사용하여 응용 프로그램으로 가져오기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로그램에 DLL에서 정의한 공용 기호가 사용될 때 해당 프로그램에서 공용 기호를 가져온다고 말합니다.  사용자의 DLL을 사용하여 빌드하는 응용 프로그램에 대해 헤더 파일을 만들 때에는 공용 기호의 선언에 **\_\_declspec\(dllimport\)**을 사용합니다.  **\_\_declspec\(dllimport\)** 키워드는 내보내기에 .def 파일을 사용하는 경우와 **\_\_declspec\(dllexport\)** 키워드를 사용하는 경우 모두에 작동합니다.  
  
 코드를 읽기 쉽게 만들려면 다음과 같이 **\_\_declspec\(dllimport\)**에 대한 매크로를 정의한 다음 이 매크로를 사용하여 가져오는 각 기호를 선언합니다.  
  
```  
#define DllImport   __declspec( dllimport )  
  
DllImport int  j;  
DllImport void func();  
```  
  
 함수 선언에서 **\_\_declspec\(dllimport\)**은 사용하지 않아도 되지만, 이 키워드를 사용하면 컴파일러에서 보다 효율적인 코드를 생성할 수 있습니다.  그러나 가져오는 실행 파일이 DLL의 공용 데이터 기호 및 개체에 액세스할 수 있도록 하려면 **\_\_declspec\(dllimport\)**을 사용해야 합니다.  DLL의 사용자들은 가져오기 라이브러리에 링크해야 합니다.  
  
 DLL과 클라이언트 응용 프로그램 모두에 대해 동일한 헤더 파일을 사용할 수 있습니다.  이렇게 하려면 DLL을 빌드하는지 또는 클라이언트 응용 프로그램을 빌드하는지를 나타내는 특별한 전처리기 기호를 사용합니다.  예를 들면 다음과 같습니다.  
  
```  
#ifdef _EXPORTING  
   #define CLASS_DECLSPEC    __declspec(dllexport)  
#else  
   #define CLASS_DECLSPEC    __declspec(dllimport)  
#endif  
  
class CLASS_DECLSPEC CExampleA : public CObject  
{ ... class definition ... };  
```  
  
## 수행할 작업  
  
-   [DLL 초기화](../build/initializing-a-dll.md)  
  
## 추가 정보  
  
-   [인라인 함수 가져오기 및 내보내기](../build/importing-and-exporting-inline-functions.md)  
  
-   [상호 가져오기](../build/mutual-imports.md)  
  
## 참고 항목  
 [응용 프로그램으로 가져오기](../build/importing-into-an-application.md)