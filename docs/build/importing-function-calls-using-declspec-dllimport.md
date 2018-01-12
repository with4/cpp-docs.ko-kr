---
title: "__Declspec (dllimport)을 사용 하 여 함수 호출 가져오기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __declspec
- dllimport
dev_langs: C++
helpviewer_keywords:
- importing function calls [C++]
- dllimport attribute [C++], function call imports
- __declspec(dllimport) keyword [C++]
- function calls [C++], importing
ms.assetid: 6b53c616-0c6d-419a-8e2a-d2fff20510b3
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5553bd5e9999a4737dc258358402eb71269b9c40
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="importing-function-calls-using-declspecdllimport"></a>__declspec(dllimport)을 사용하여 함수 호출 가져오기
다음 코드 예제를 사용 하는 방법을 보여 줍니다 **_declspec(dllimport)** DLL에서 함수 호출을 응용 프로그램에 가져오려는 합니다. 가정 `func1` 포함 하는.exe 파일에서 별도 DLL에 상주 하는 함수는 **주** 함수입니다.  
  
 없이 **__declspec (dllimport)**,이 코드를 제공 합니다.  
  
```  
int main(void)   
{  
   func1();  
}  
```  
  
 컴파일러에서는 다음과 같은 코드를 생성 합니다.  
  
```  
call func1  
```  
  
 고 링커 변환으로 다음과 같이 호출:  
  
```  
call 0x4000000         ; The address of 'func1'.  
```  
  
 경우 `func1` 다른 DLL에 있는, 링커가 직접 확인할 수 없는의 주소를 알 수 없으므로 있기 때문에 `func1` 됩니다. 16 비트 환경 링커가 올바른 주소로 런타임 시 로더가 패치 하 게 하는.exe 파일의 목록에이 코드 주소를 추가 합니다. 32 비트 및 64 비트 환경 링커 주소를 알고 있으며 썽크를 생성 합니다. 32 비트 환경에서 썽크는 다음과 같습니다.  
  
```  
0x40000000:    jmp DWORD PTR __imp_func1  
```  
  
 여기 `imp_func1` 의 주소는는 `func1` .exe 파일의 가져오기 주소 테이블의 슬롯입니다. 따라서 모든 주소는 링커에 알 수 있습니다. 로더만에서 제대로 작동 하려면 모든 항목에 대 한 로드 시간에.exe 파일 가져오기 주소 테이블을 업데이트 해야 합니다.  
  
 따라서 사용 하 여 **__declspec (dllimport)** 이 더 좋습니다 필요 하지 않은 경우 링커는 썽크를 생성 하지 않습니다. 썽크는 코드의 길이 더 큰 (RISC 시스템에서는 여러 가지 명령이 될 수 있음) 캐시 성능을 저하 시킬 수 있습니다. DLL에서 함수는 컴파일러가 지시를 사용자에 대 한 간접 호출을 발생할 수 있습니다.  
  
 이제이 코드:  
  
```  
__declspec(dllimport) void func1(void);  
int main(void)   
{  
   func1();  
}  
```  
  
 이 명령을 생성 합니다.  
  
```  
call DWORD PTR __imp_func1  
```  
  
 썽크 및 아니요 `jmp` 명령 코드 크기가 작고 속도가 빠르기 때문입니다.  
  
 반면에 DLL 내 함수 호출에 대 한 하지 않으려는 경우 간접 호출을 사용 해야 합니다. 이미 함수의 주소를 알고 있습니다. 시간과 공간 로드 하 고 간접 호출 전에 함수의 주소를 저장할 필요를 직접 호출 이므로 항상 빠르고 작은 합니다. 사용 하려는 **__declspec (dllimport)** 자체 DLL 외부에서 DLL 함수를 호출할 때입니다. 사용 하지 마십시오 **__declspec (dllimport)** 해당 DLL을 빌드할 때 DLL 내부 함수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [응용 프로그램으로 가져오기](../build/importing-into-an-application.md)