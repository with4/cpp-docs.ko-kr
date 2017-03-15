---
title: "명시적 링크 | Microsoft Docs"
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
ms.assetid: 1e13d960-a195-4e6d-9864-7d8f3a701f4b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 명시적 링크
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

명시적 링크의 경우에는 응용 프로그램이 런타임에 함수를 호출하여 DLL을 명시적으로 로드해야 합니다.  DLL에 명시적으로 링크하려면 응용 프로그램은 다음과 같은 작업을 수행해야 합니다.  
  
-   **LoadLibrary** 또는 이와 유사한 함수를 호출하여 DLL을 로드하고 모듈 핸들을 가져와야 합니다.  
  
-   **GetProcAddress**를 호출하여 응용 프로그램이 호출하려는 각각의 내보내기 함수에 대한 함수 포인터를 가져와야 합니다.  응용 프로그램에서는 포인터를 통해 DLL의 함수를 호출하기 때문에 컴파일러는 외부 참조를 생성하지 않습니다. 따라서 가져오기 라이브러리와 링크할 필요도 없습니다.  
  
-   DLL을 사용할 필요가 없으면 **FreeLibrary**를 호출해야 합니다.  
  
 예를 들면 다음과 같습니다.  
  
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
  
## 수행할 작업  
  
-   [암시적 링크](../build/linking-implicitly.md)  
  
-   [사용할 링크 방법 결정](../build/determining-which-linking-method-to-use.md)  
  
## 추가 정보  
  
-   [LoadLibrary 및 AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
-   [FreeLibrary 및 AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)  
  
-   [Windows에서 DLL을 찾는 데 사용되는 검색 경로](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
## 참고 항목  
 [DLL에 실행 파일 링크](../build/linking-an-executable-to-a-dll.md)