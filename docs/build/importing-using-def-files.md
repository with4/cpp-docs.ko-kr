---
title: DEF 파일을 사용 하 여 가져오기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- importing DLLs [C++], DEF files
- def files [C++], importing with
- .def files [C++], importing with
- dllimport attribute [C++], DEF files
- DLLs [C++], DEF files
ms.assetid: aefdbf50-f603-488a-b0d7-ed737bae311d
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ee213f1aa381415444288dbab4473cae6f5fc7b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="importing-using-def-files"></a>DEF 파일을 사용하여 가져오기
사용 하려는 경우 **__declspec (dllimport)** .def 파일을 함께.def 파일 상수 대신 데이터를 사용 하 여 잘못 된 코딩 문제가 발생할 수 가능성을 변경 해야 합니다.  
  
```  
// project.def  
LIBRARY project  
EXPORTS  
   ulDataInDll   DATA  
```  
  
 다음 표에서 이유를 보여 줍니다.  
  
|키워드|가져오기 라이브러리의 내보내기|내보내기|  
|-------------|---------------------------------|-------------|  
|`CONSTANT`|`_imp_ulDataInDll`, `_ulDataInDll`|`_ulDataInDll`|  
|`DATA`|`_imp_ulDataInDll`|`_ulDataInDll`|  
  
 사용 하 여 **__declspec (dllimport)** 상수를 모두 나열 하 고는 `imp` 데코 레이트 되지 않은.lib DLL 이름 및 버전에 대 한 가져오기 라이브러리 명시적 링크를 허용 하기 위해 만든 합니다. 사용 하 여 **__declspec (dllimport)** 및 목록 데이터 요소만 `imp` 이름의 버전입니다.  
  
 상수를 사용 하는 경우 중 한 다음 코드 구문을 사용할 수 있습니다에 액세스 하려면 `ulDataInDll`:  
  
```  
__declspec(dllimport) ULONG ulDataInDll; /*prototype*/  
if (ulDataInDll == 0L)   /*sample code fragment*/  
```  
  
 또는  
  
```  
ULONG *ulDataInDll;      /*prototype*/  
if (*ulDataInDll == 0L)  /*sample code fragment*/  
```  
  
 그러나.def 파일에 데이터를 사용 하는 경우 다음 정의 사용 하 여 컴파일한 코드 에서만 변수에 액세스할 수 `ulDataInDll`:  
  
```  
__declspec(dllimport) ULONG ulDataInDll;  
  
if (ulDataInDll == 0L)   /*sample code fragment*/  
```  
  
 상수를 사용 하는 변수에 대 한 가져오기 주소 테이블 포인터 추가 수준의 간접 참조를 사용 하지 않으면 잠재적으로 액세스할 수 있으므로 더 위험-변수 자체입니다. 이러한 유형의 문제 되기 때문에 가져오기 주소 테이블이 현재 읽기 전용 컴파일러 및 링커 액세스 위반으로 매니페스트 종종 수 있습니다.  
  
 이 경우에 대 한 설명 하기 위해 상수.def 파일의 경우 현재 Visual c + + 링커는 경고가 발생 합니다. 상수를 사용 하는 유일한 이유는 헤더 파일에 나열 되지 않은 일부 개체 파일을 다시 컴파일할 수 없는 경우 **__declspec (dllimport)** 프로토타입을에 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [응용 프로그램으로 가져오기](../build/importing-into-an-application.md)
