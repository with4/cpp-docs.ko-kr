---
title: "C++에서 명시적 PInvoke 사용(DllImport 특성) | Microsoft Docs"
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
  - "C++ Interop, 플랫폼 호출"
  - "데이터 마샬링[C++], 플랫폼 호출"
  - "interop[C++], 플랫폼 호출"
  - "마샬링[C++], 플랫폼 호출"
  - "플랫폼 호출[C++], C++에서 마샬링"
ms.assetid: 18e5218c-6916-48a1-a127-f66e22ef15fc
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++에서 명시적 PInvoke 사용(DllImport 특성)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

.NET Framework는 DLL 안에 패키지된 관리되지 않는 함수를 관리되는 응용 프로그램에서 호출할 수 있도록 `Dllimport` 특성과 함께 명시적 플랫폼 호출\(PInvoke\) 기능을 제공합니다.  관리되지 않는 API가 DLL로 패키지되어 있어서 소스 코드를 사용할 수 없는 경우 명시적 PInvoke가 필요합니다.  예를 들어 Win32 함수를 호출하려면 PInvoke가 필요합니다.  그렇지 않은 경우 암시적인 P{Invoke를 사용합니다. 자세한 내용은 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)을 참조하십시오.  
  
 PInvoke는 <xref:System.Runtime.InteropServices.DllImportAttribute>를 통해 작동합니다.  이 특성은 DLL 이름을 첫 번째 인수로 사용하며 사용될 각 DLL 진입점에 대한 함수 선언 앞에 놓입니다.  함수의 시그니처는 DLL에서 내보내는 함수의 이름과 일치해야 합니다. 그러나 관리되는 형식을 사용하여 `DllImport` 선언을 정의하면 일부 형식 변환을 암시적으로 수행할 수 있습니다.  
  
 그 결과로 각 네이티브 DLL 함수에 대한 관리되는 진입점이 만들어집니다. 이 진입점에는 필요한 전환 코드\(또는 썽크\) 및 단순 데이터 변환이 포함됩니다.  관리되는 함수에서는 이들 진입점을 통해 DLL을 호출할 수 있습니다.  PInvoke의 결과로 모듈에 삽입되는 코드는 전적으로 관리 코드이고, 명시적 PInvoke는 **\/clr**, **\/clr:pure** 및 **\/clr:safe** 컴파일에서 지원됩니다.  자세한 내용은 [순수형 및 안정형 코드](../dotnet/pure-and-verifiable-code-cpp-cli.md)을 참조하십시오.  
  
## 단원 내용  
  
-   [관리 코드에서 네이티브 함수 호출](../dotnet/calling-native-functions-from-managed-code.md)  
  
-   [방법: PInvoke를 사용하여 관리 코드로부터 네이티브 DLL 호출](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)  
  
-   [방법: PInvoke를 사용하여 문자열 마샬링](../dotnet/how-to-marshal-strings-using-pinvoke.md)  
  
-   [방법: PInvoke를 사용하여 구조체 마샬링](../dotnet/how-to-marshal-structures-using-pinvoke.md)  
  
-   [방법: PInvoke를 사용하여 배열 마샬링](../dotnet/how-to-marshal-arrays-using-pinvoke.md)  
  
-   [방법: PInvoke를 사용하여 함수 포인터 마샬링](../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)  
  
-   [방법: PInvoke를 사용하여 포함 포인터 마샬링](../dotnet/how-to-marshal-embedded-pointers-using-pinvoke.md)  
  
## 참고 항목  
 [관리 코드에서 네이티브 함수 호출](../dotnet/calling-native-functions-from-managed-code.md)