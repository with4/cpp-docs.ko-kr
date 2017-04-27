---
title: "링커 도구 오류 LNK1561 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1561
dev_langs:
- C++
helpviewer_keywords:
- LNK1561
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: fbc63a58cd4e276aa2a3f77baeea07d1912eda98
ms.lasthandoff: 04/24/2017

---
# <a name="linker-tools-error-lnk1561"></a>링커 도구 오류 LNK1561
진입점이 정의되어야 합니다.  
  
링커는 진입점을 찾지 못했습니다. 이 오류는 여러 가지 원인이 있을 수 있습니다.  
-   연결할 파일 목록에서 프로그램 진입점을 정의 하는 파일을 포함 하지 않을 수 있습니다. 진입점 함수를 포함 하는 파일은 앱에 연결 되어 있는 확인 하십시오.  
-   잘못 된 함수 시그니처;를 사용 하 여 시작 지점 정의 예를 들어 수 철자가 잘못 입력 된 또는 함수 이름에 잘못 된 대/소문자를 사용 했거나 반환 형식 또는 형식 매개 변수를 올바르게 지정 합니다. 기본적으로 링커는에 대 한 검색 한 `main` 또는 `wmain` 콘솔 응용 프로그램에 대 한 함수는 `WinMain` 또는 `wWinMain` Windows 앱에 대 한 함수 또는 `DllMain` 초기화 작업을 수행 하는 DLL에 대 한 합니다.  
-   지정 하지는 [/DLL](../../build/reference/dll-build-a-dll.md) DLL을 빌드할 때 옵션입니다.  
-   수 하지 진입점 함수의 이름을 올바르게 지정을 사용할 때의 [/ENTRY](../../build/reference/entry-entry-point-symbol.md) 링커 옵션입니다.  
-   사용 하는 경우는 [LIB](../../build/reference/lib-reference.md) dll을 도구를.def 파일을 지정 했습니다. 이 경우 빌드에서.def 파일을 제거 합니다.    
  
링커는 검색 응용 프로그램을 빌드하는 경우는 *진입점*, 코드를 시작 하 여 함수를 호출 합니다. 응용 프로그램이 로드 되 고 런타임에 초기화 후에 호출 되는 함수입니다. 응용 프로그램에 대 한 진입점 함수를 제공 해야 하거나 응용 프로그램을 실행할 수 없습니다. 진입점은 DLL에 대 한 선택 사항입니다. 기본적으로 링커 중 하나가 있는 몇 가지 특정 이름 및 서명을 같은 진입점 함수에 대 한 찾습니다 `int main(int, char**)`합니다. 항목으로 다른 함수 이름을 지정할 수 있습니다 /ENTRY 링커 옵션을 사용 하 여 지점입니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 LNK1561 오류가 생성 됩니다.  
  
```cpp  
// LNK1561.cpp  
// LNK1561 expected  
int i;  
// add a main function to resolve this error  
```
