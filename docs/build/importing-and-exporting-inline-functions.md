---
title: 가져오기 및 내보내기 인라인 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- exporting functions [C++], inline functions
- inline functions [C++], importing
- DLLs [C++], importing
- importing functions [C++]
- DLLs [C++], exporting from
- importing inline functions [C++]
- inline functions [C++], exporting
- functions [C++], importing
- functions [C++], exporting
ms.assetid: 89f488f8-b078-40fe-afd7-80bd7840057b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b666d450766a5a285f02517d92d5eb4dc3f29c68
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368579"
---
# <a name="importing-and-exporting-inline-functions"></a>인라인 함수 가져오기 및 내보내기
가져온된 함수를 인라인으로 정의할 수 있습니다. 효과 거의 표준 함수 인라인;와 동일 함수 호출에는 인라인 코드로 매크로 매우 유사 하 게 확장 됩니다. C + +를 지 원하는 효율성에 대 한 함수 일부 멤버를 인라인 할 수 있는 DLL의 클래스 주로 유용 합니다.  
  
 가져온된 인라인 함수에의 한 가지 특징은 c + +에서 해당 주소를 취할 수 있습니다. 컴파일러는 DLL에 상주 하는 인라인 함수의 복사본의 주소를 반환 합니다. 다른의 가져온된 인라인 함수 기능은 글로벌 가져온된 데이터와 달리 가져온 함수의 정적 로컬 데이터를 초기화할 수 있습니다.  
  
> [!CAUTION]
>  버전 충돌 가능성을 만들 수 있기 때문에 가져온 인라인 함수를 제공 하는 경우 주의 기울여야 합니다. 응용 프로그램 코드;으로 인라인 함수 확장 따라서 함수를 나중에 다시 작성할 때이 업데이트 되지 않습니다 응용 프로그램 자체를 다시 컴파일할 하지 않는 한 합니다. (일반적으로 DLL 함수 업데이트할 수 있습니다을 사용 하는 응용 프로그램을 다시 작성 하지 않고.)  
  
## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.  
  
-   [DLL에서 내보내기](../build/exporting-from-a-dll.md)  
  
-   [사용 하 여 DLL에서 내보냅니다. DEF 파일](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [__Declspec (dllexport)를 사용 하 여 DLL에서 내보내기](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX_EXT_CLASS를 사용 하 여 가져오기 및 내보내기](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C 언어 실행 파일에서 사용 하기 위해 c + + 함수 내보내기](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [사용할 내보내기 방법 결정](../build/determining-which-exporting-method-to-use.md)  
  
-   [__Declspec (dllimport)을 사용 하 여 응용 프로그램으로 가져오기](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
## <a name="see-also"></a>참고 항목  
 [가져오기 및 내보내기](../build/importing-and-exporting.md)