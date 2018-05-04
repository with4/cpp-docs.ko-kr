---
title: GetProcAddress | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- GetProcAddress
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], GetProcAddress
- ordinal exports [C++]
- GetProcAddress method
ms.assetid: 48d14ae0-47ea-4c5d-96b1-2c158f1a26af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cec73a7d7aa212c6f53bc2654db6fe40ff96472a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="getprocaddress"></a>GetProcAddress
DLL 호출에 명시적으로 연결 하는 프로세스 [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212) DLL에서 내보낸된 함수 주소를 가져옵니다. 반환 된 함수 포인터를 사용 하 여 DLL 함수를 호출 합니다. **GetProcAddress** DLL 모듈 핸들을 매개 변수로 (에서 반환 된 **LoadLibrary**, `AfxLoadLibrary`, 또는 **GetModuleHandle**) 원하는 함수 이름을 사용 하 고 호출 하거나 함수 내보내기 서 수를 제공 합니다.  
  
 포인터를 통해 DLL 함수를 호출 하는 없으므로 컴파일 타임 형식 검사는 한도가 스택에 할당 된 메모리 및에서 액세스 위반이 발생 하지 않는 함수에 매개 변수가 정확한 지 확인 합니다. 형식 안전성을 보장 하는 한 가지 방법은 내보낸 함수의 함수 프로토타입을 확인 하 고 함수 포인터에 대 한 일치 하는 형식 정의 만드는 경우 예를 들어:  
  
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
  
 호출할 때 원하는 함수를 지정 하는 방법 **GetProcAddress** DLL 작성 된 방법에 따라 달라 집니다.  
  
 모듈 정의 (.def) 파일을 사용 하 여 연결할 DLL 빌드 및 서 수의 함수와 함께 나열 된 경우에 내보내기 서 수를 가져올 수 있습니다는 **내보내기** DLL의.def 파일의 섹션입니다. 호출 **GetProcAddress** 내보내기 된 함수 이름이 아닌 서 수는 경우 DLL 내보내기 테이블 dll과 DLL로 인덱스 처럼 사용 하기 때문에 많은 내보낸된 함수에 약간 더 빠릅니다. 내보내기는 서 수와 **GetProcAddress** DLL의 내보내기 테이블의 함수 이름에 지정된 된 이름을 이름과 비교 함수를 찾을 수 있습니다. 하지만 호출 해야 **GetProcAddress** 내보내기 서 수는.def 파일의 내보낸된 함수에는 서 수를 지정 하는 작업을 제어할 수 있는 경우에 사용 합니다.  
  
## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.  
  
-   [암시적으로 DLL에 연결 하는 방법](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [사용할 연결 방법을 결정 합니다.](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [LoadLibrary 및 AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [FreeLibrary](http://msdn.microsoft.com/library/windows/desktop/ms683152)  
  
-   [DEF 파일을 사용하여 DLL에서 내보내기](../build/exporting-from-a-dll-using-def-files.md)  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++의 DLL](../build/dlls-in-visual-cpp.md)