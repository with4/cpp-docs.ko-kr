---
title: "GetProcAddress | Microsoft Docs"
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
  - "GetProcAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL[C++], GetProcAddress"
  - "GetProcAddress 메서드"
  - "서수 내보내기[C++]"
ms.assetid: 48d14ae0-47ea-4c5d-96b1-2c158f1a26af
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# GetProcAddress
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DLL에 명시적으로 링크하는 프로세스는 [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212)를 호출하여 해당 DLL에 있는 내보낸 함수의 주소를 가져옵니다.  이렇게 반환된 함수 포인터를 사용하여 DLL 함수를 호출합니다.  **GetProcAddress**는 **LoadLibrary**, `AfxLoadLibrary` 또는 **GetModuleHandle**에서 반환하는 DLL 모듈 핸들을 매개 변수로 사용하고 호출하려는 함수의 이름 또는 함수의 내보내기 서수를 전달받습니다.  
  
 DLL 함수는 포인터를 통해 호출하며 컴파일 타임 형식 검사가 수행되지 않으므로, 이 함수에 대한 매개 변수가 정확해야만 스택에 할당되는 메모리 한도가 초과되거나 액세스 위반이 발생하지 않게 됩니다.  형식 안전성을 보장하는 한 가지 방법은 내보내기 함수의 함수 프로토타입을 확인하고 해당 함수 포인터에 맞는 형식 정의\(typedef\)를 만드는 것입니다.  예를 들면 다음과 같습니다.  
  
```  
typedef UINT (CALLBACK* LPFNDLLFUNC1)(DWORD,UINT);  
...  
  
HINSTANCE hDLL;               // Handle to DLL  
LPFNDLLFUNC1 lpfnDllFunc1;    // Function pointer  
DWORD dwParam1;  
UINT  uParam2, uReturnVal;  
  
hDLL = LoadLibrary("MyDLL");  
if (hDLL != NULL)  
{  
   lpfnDllFunc1 = (LPFNDLLFUNC1)GetProcAddress(hDLL,  
                                           "DLLFunc1");  
   if (!lpfnDllFunc1)  
   {  
      // handle the error  
      FreeLibrary(hDLL);  
      return SOME_ERROR_CODE;  
   }  
   else  
   {  
      // call the function  
      uReturnVal = lpfnDllFunc1(dwParam1, uParam2);  
   }  
}  
```  
  
 **GetProcAddress**를 호출할 때 필요한 함수를 지정하는 방법은 해당 DLL의 빌드 방법에 따라 다릅니다.  
  
 링크하려는 DLL이 모듈 정의 파일\(.def\)을 사용하여 빌드되었고 내보내기 서수가 해당 함수와 함께 이 DLL의 .def 파일에 있는 **EXPORTS** 섹션에 나열된 경우에는 내보내기 서수만 가져올 수 있습니다.  내보내기 서수는 해당 DLL의 내보내기 테이블에서 인덱스로 사용되기 때문에 DLL에 내보내기 함수가 많은 경우 내보내기 서수를 사용하여 **GetProcAddress**를 호출하면 함수 이름을 사용할 때와는 달리 처리 속도가 약간 빨라집니다.  함수 이름을 사용할 경우 지정된 이름을 DLL의 내보내기 테이블에 있는 함수 이름과 비교해야 하는 반면 내보내기 서수를 사용할 경우에는 **GetProcAddress**에서 함수를 곧바로 찾을 수 있습니다.  그러나 .def 파일의 내보내기 함수에 대한 서수 할당을 제어할 수 있는 경우에만 내보내기 함수를 사용하여 **GetProcAddress**를 호출해야 합니다.  
  
## 수행할 작업  
  
-   [암시적 링크](../build/linking-implicitly.md)  
  
-   [사용할 링크 방법 결정](../build/determining-which-linking-method-to-use.md)  
  
## 추가 정보  
  
-   [LoadLibrary 및 AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [\<caps:sentence id\="tgt17" sentenceid\="8c920606bb67e2587dd3c3e5cf977593" class\="tgtSentence"\>FreeLibrary\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms683152)  
  
-   [DEF 파일을 사용하여 DLL에서 내보내기](../build/exporting-from-a-dll-using-def-files.md)  
  
## 참고 항목  
 [Visual C\+\+의 DLL](../build/dlls-in-visual-cpp.md)