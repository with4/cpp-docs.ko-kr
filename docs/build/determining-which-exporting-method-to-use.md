---
title: "사용할 내보내기 방법 결정 | Microsoft Docs"
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
  - ".def 파일[C++], DLL에서 내보내기"
  - "__declspec(dllexport) 키워드[C++]"
  - "def 파일[C++], DLL에서 내보내기"
  - "DLL 내보내기[C++], 메서드 비교"
ms.assetid: 66d773ed-935c-45c2-ad03-1a060874b34d
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 사용할 내보내기 방법 결정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

You can export functions in either of two ways—a .def file or the `__declspec(dllexport)` keyword.  To help you decide which way is better for your DLL, consider these questions:  
  
-   Do you plan to export more functions later?  
  
-   Is your DLL used only by applications that you can rebuild, or is it used by applications that you cannot rebuild—for example, applications that are created by third parties?  
  
## Pros and Cons of Using .def Files  
 Exporting functions in a .def file gives you control over the export ordinals.  When you add an exported function to your DLL, you can assign it a higher ordinal value than any other exported function.  When you do this, applications that use implicit linking do not have to relink with the import library that contains the new function.  This is very convenient if you are designing a DLL for use by many applications because you can add new functionality and also ensure that it continues to work correctly with the applications that already rely on it.  For example, the MFC DLLs are built by using .def files.  
  
 Another advantage to using a .def file is that you can use the `NONAME` attribute to export a function.  This puts only the ordinal in the exports table in the DLL.  For DLLs that have a large number of exported functions, using the `NONAME` attribute can reduce the size of the DLL file.  For information about how to write a module definition statement, see [모듈 정의 문의 규칙](../build/reference/rules-for-module-definition-statements.md).  For information about ordinal export, see [이름 대신 서수를 사용하여 DLL에서 함수 내보내기](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).  
  
 A disadvantage of using a .def file is that if you are exporting functions in a C\+\+ file, you either have to put the decorated names in the .def file or define the exported functions by using extern "C" to avoid the name decoration that's done by the Visual C\+\+ compiler.  
  
 If you put the decorated names in the .def file, you can obtain them by using the [DUMPBIN](../build/reference/dumpbin-reference.md) tool or by using the linker [\/MAP](../build/reference/map-generate-mapfile.md) option.  The decorated names that are produced by the compiler are compiler\-specific; therefore, if you put the decorated names that are produced by the compiler into a .def file, the applications that link to the DLL must also be built by using the same version of the compiler so that the decorated names in the calling application match the exported names in the .def file of the DLL.  
  
## \_\_declspec\(dllexport\) 사용의 장단점  
 Using `__declspec(dllexport)` is convenient because you do not have to worry about maintaining a .def file and obtaining the decorated names of the exported functions.  However, the usefulness of this way of exporting is limited by the number of linked applications that you are willing to rebuild.  If you rebuild the DLL with new exports, you also have to rebuild the applications because the decorated names for exported C\+\+ functions might change if you use a different version of the compiler to rebuild it.  
  
### 수행할 작업  
  
-   [.DEF 파일을 사용하여 DLL에서 내보내기](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [\_\_declspec\(dllexport\)을 사용하여 DLL에서 내보내기](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX\_EXT\_CLASS를 사용하여 내보내기 및 가져오기](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C\+\+ 함수를 C 언어 실행 파일에서 사용할 수 있도록 내보내기](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [C 함수를 C 또는 C\+\+ 언어 실행 파일에서 사용할 수 있도록 내보내기](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [\_\_declspec\(dllimport\)을 사용하여 응용 프로그램으로 가져오기](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL 초기화](../build/initializing-a-dll.md)  
  
### 추가 정보  
  
-   [인라인 함수 가져오기 및 내보내기](../build/importing-and-exporting-inline-functions.md)  
  
-   [상호 가져오기](../build/mutual-imports.md)  
  
-   [데코레이팅된 이름](../build/reference/decorated-names.md)  
  
## 참고 항목  
 [DLL에서 내보내기](../build/exporting-from-a-dll.md)