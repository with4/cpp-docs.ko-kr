---
title: 컴파일러 오류 C3646 | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3646
dev_langs:
- C++
helpviewer_keywords:
- C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c038520c1a35fa5264e1e98b074687efb336d028
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "35658613"
---
# <a name="compiler-error-c3646"></a>컴파일러 오류 C3646

> 'specifier': 알 수 없는 재정의 지정자

## <a name="remarks"></a>설명

컴파일러는 재정의 지정자를 찾을 것으로 예상 했지만 토큰 컴파일러에서 인식할 수 없습니다 위치에는 토큰을 찾았습니다.

예를 들어 경우를 인식할 수 없는 *지정자* 됩니다 **_NOEXCEPT**, 키워드로 대체 **noexcept**합니다.

자세한 내용은 [재정의 지정자](../../windows/override-specifiers-cpp-component-extensions.md)합니다.

## <a name="example"></a>예

다음 샘플 C3646 생성 및이 해결 하는 방법을 보여 줍니다.

```cpp
// C3646.cpp
// compile with: /clr /c
ref class C {
   void f() unknown;   // C3646
   // try the following line instead
   // virtual void f() abstract;
};
```