---
title: "링커 도구 오류 LNK2022 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2022
dev_langs:
- C++
helpviewer_keywords:
- LNK2022
ms.assetid: d2128c73-dde3-4b8e-a9b2-0a153acefb3b
caps.latest.revision: 15
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 6f12c53d7dd1383ad8f994a713c7226ab038cb19
ms.lasthandoff: 04/01/2017

---
# <a name="linker-tools-error-lnk2022"></a>링커 도구 오류 LNK2022
메타 데이터 작업 (HRESULT)에 실패 했습니다: error_message  
  
 메타 데이터를 병합 하는 동안 링커 오류가 발생 했습니다. 성공적으로 연결 하는 메타 데이터 오류를 해결 해야 합니다.  
  
 실행 하는 것이 문제를 진단 하는 한 가지 방법은 **ildasm-토큰** 에 나열 된 토큰 형식을 확인을 개체 파일에 `error_message`, 차이점을 찾습니다.  메타 데이터에서 이름이 같은 두 가지 유형이 올바르지 정당한 LayoutType 특성은 서로 다른 경우에 합니다.  
  
 LNK2022가 형식 (예: 구조체)에 충돌 하는 정의 하지만 같은 이름의 여러 번 발생 하 고 사용 하 여 컴파일하면 이유 하나 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)합니다.  이 경우 모든 컴파일 대상에 유형 정의가 동일한 있는지 확인 합니다.  형식 이름에 나열 된 `error_message`합니다.  
  
 LNK2022에 대 한 또 다른 원인으로 링커는 컴파일러에 지정한 것을 다른 위치에 있는 메타 데이터 파일을 찾은 경우 (으로 [#using](../../preprocessor/hash-using-directive-cpp.md) ). 메타데이터 파일(.dll 또는 .netmodule)이 링커에 전달될 때에도 컴파일러에 전달되었을 때 있던 것과 동일한 위치에 있는지 확인합니다.  
  
 ATL 응용 프로그램을 빌드할 때 [>_atl_mixed](http://msdn.microsoft.com/Library/11b59a83-7098-43e2-9f7b-408299930966) 하나 이상에 사용 되는 경우 모든 컴파일 대상에 필요 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에는 빈 형식을 정의합니다.  
  
```  
// LNK2022_a.cpp  
// compile with: /clr /c  
public ref class Test {};  
```  
  
## <a name="example"></a>예제  
 이 예제를 보여 줍니다 유형의 이름은 같지만 서로 다른 정의 포함 하는 두 개의 소스 코드 파일에 연결할 수 없습니다.  
  
 다음 샘플에서는 LNK2022 합니다.  
  
```  
// LNK2022_b.cpp  
// compile with: LNK2022_a.cpp /clr /LD   
// LNK2022 expected  
public ref class Test {  
   void func() {}  
   int var;  
};  
```
