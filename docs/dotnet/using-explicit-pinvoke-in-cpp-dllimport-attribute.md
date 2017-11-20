---
title: "C + + (DllImport 특성)에서 명시적 PInvoke 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- marshaling [C++], platform invoke
- C++ Interop, platform invoke
- interop [C++], platform invoke
- platform invoke [C++], marshaling in C++
- data marshaling [C++], platform invoke
ms.assetid: 18e5218c-6916-48a1-a127-f66e22ef15fc
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5b3b2c69e022de6420223786f0f3b3f266c4f816
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="using-explicit-pinvoke-in-c-dllimport-attribute"></a>C++에서 명시적 PInvoke 사용(DllImport 특성)
.NET Framework 명시적 플랫폼 호출 (또는 PInvoke) 기능을 제공 하는 `Dllimport` Dll 패키지 된 관리 되지 않는 함수를 호출 하는 관리 되는 응용 프로그램을 허용 하는 특성입니다. 명시적 PInvoke는 관리 되지 않는 Api는 Dll로 패키지 하 고 소스 코드를 사용할 수 있는 경우 필요 합니다. PInvoke 필요 예를 들어 Win32 함수를 호출 합니다. 그렇지 않은 경우 암시적 P을 사용 하 여 {Invoke; 참조 [c + + Interop를 사용 하 여 (암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md) 자세한 정보에 대 한 합니다.  
  
 PInvoke를 사용 하 여 작동 <xref:System.Runtime.InteropServices.DllImportAttribute>합니다. 첫 번째 인수로 DLL의 이름을 가져오는,이 특성에 사용 되는 각 DLL 진입점에 대 한 함수 선언 앞에 배치 됩니다. 함수의 서명이 DLL에서 내보낸 함수의 이름이 일치 해야 합니다 (일부 형식 변환을 정의 하 여 암시적으로 수행할 수 있지만 `DllImport` 관리 되는 형식으로 선언 합니다.)  
  
 결과 필요한 전환 코드 (또는 썽크)가 포함 된 각 네이티브 DLL 함수에 대 한 관리 되는 진입점 및 단순한 데이터 변환 합니다. 이러한 진입점을 통해 DLL로 관리 되는 함수를 호출할 수 있습니다. PInvoke 결과 완전 하 게 관리 하 고 명시적 PInvoke에 대해 지원 되는 모듈에 삽입 된 코드 **/clr**, **/clr: pure**, 및 **/clr: safe** 컴파일 합니다. **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않습니다. 자세한 내용은 참조 [순수형 및 안정형 코드 (C + + /cli CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)합니다.  
  
## <a name="in-this-section"></a>단원 내용  
  
-   [관리 코드에서 네이티브 함수 호출](../dotnet/calling-native-functions-from-managed-code.md)  
  
-   [방법: PInvoke를 사용하여 관리 코드로부터 네이티브 DLL 호출](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)  
  
-   [방법: PInvoke를 사용하여 문자열 마샬링](../dotnet/how-to-marshal-strings-using-pinvoke.md)  
  
-   [방법: PInvoke를 사용하여 구조체 마샬링](../dotnet/how-to-marshal-structures-using-pinvoke.md)  
  
-   [방법: PInvoke를 사용하여 배열 마샬링](../dotnet/how-to-marshal-arrays-using-pinvoke.md)  
  
-   [방법: PInvoke를 사용하여 함수 포인터 마샬링](../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)  
  
-   [방법: PInvoke를 사용하여 포함 포인터 마샬링](../dotnet/how-to-marshal-embedded-pointers-using-pinvoke.md)  
  
## <a name="see-also"></a>참고 항목  
 [관리 코드에서 네이티브 함수 호출](../dotnet/calling-native-functions-from-managed-code.md)