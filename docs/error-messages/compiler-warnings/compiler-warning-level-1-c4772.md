---
title: "컴파일러 경고 (수준 1) C4772 | Microsoft Docs"
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: error-reference
f1_keywords:
- C4772
dev_langs:
- C++
helpviewer_keywords:
- C4772
ms.assetid: dafe6fd8-9faf-41f5-9d66-a55838742c14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 631cd4f872c7b8912b791417c04f6c6e9e056bdd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4772"></a>컴파일러 경고(수준 1) C4772

> \#누락 된 형식 라이브러리;에서 형식을 참조 하는 가져오기 '*누락 형*' 자리 표시자로 사용

으로 참조 된 형식 라이브러리는 [#import](../../preprocessor/hash-import-directive-cpp.md) 지시문입니다. 형식 라이브러리와 참조 되지 않은 다른 형식 라이브러리에 대 한 참조를 포함 하는 반면 `#import`합니다. 컴파일러에 의해가이.tlb 파일을 찾을 수 없습니다.

컴파일러는 하지 되어 형식 라이브러리 서로 다른 디렉터리에 사용 하는 경우는 [/I (추가 포함 디렉터리)](../../build/reference/i-additional-include-directories.md) 컴파일러 옵션을이 디렉터리를 지정 합니다. 컴파일러에 다른 디렉터리에서 형식 라이브러리를 검색 하려는 경우 해당 디렉터리를 PATH 환경 변수를 추가 합니다.

기본적으로이 경고는 오류로 발생 합니다. /W0 C4772는 억제할 수 없습니다.

## <a name="example"></a>예

이것이 C4772 재현 하기 위한 첫 번째 형식 라이브러리입니다.

```IDL
// c4772a.idl
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]
library C4772aLib
{
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c100")]
   enum E_C4772a
   {
      one, two, three
   };
};
```

이것이 C4772 재현 하기 위한 두 번째 형식 라이브러리입니다.

```IDL
// c4772b.idl
// post-build command: del /f C4772a.tlb
// C4772a.tlb is available when c4772b.tlb is built
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]
library C4772bLib
{
   importlib ("c4772a.tlb");
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]
   struct S_C4772b
   {
      enum E_C4772a e;
   };
};
```

다음 샘플에서는 C4772 오류가 생성 됩니다.

```cpp
// C4772.cpp
// assumes that C4772a.tlb is not available to the compiler
// #import "C4772a.tlb"
#import "C4772b.tlb"   // C4772 uncomment previous line to resolve
                       // and make sure c4772a.tlb is on disk
```