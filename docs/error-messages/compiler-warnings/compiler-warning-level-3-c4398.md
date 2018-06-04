---
title: 컴파일러 경고 (수준 3) C4398 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4398
dev_langs:
- C++
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c38ade6b75242fdd5144481e3415e914cb6773c5
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704616"
---
# <a name="compiler-warning-level-3-c4398"></a>컴파일러 경고(수준 3) C4398

> '*변수*': appdomain이 여러 개 프로세스별 전역 개체가 제대로 작동 하지 않으면 __declspec (appdomain)을 사용 하는 것이 좋습니다.

## <a name="remarks"></a>설명

갖는 가상 함수와 [__clrcall](../../cpp/clrcall.md) 를 네이티브 형식에 규칙을 호출 하면 생성 된 별로 응용 프로그램 도메인 vtable 합니다. 여러 응용 프로그램 도메인에서 사용 될 때 이러한 변수 올바르게 해결할 수는 없습니다.

명시적으로 변수를 표시 하 여이 경고를 해결할 수 `__declspec(appdomain)`합니다. Visual Studio 2017 하기 전에 Visual Studio의 버전을 사용 하 여 컴파일하면이 경고를 해결할 수 **/clr: pure**, 기본적으로 appdomain 당 전역 변수를 만드는 합니다. **/clr: pure** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

자세한 내용은 참조 [appdomain](../../cpp/appdomain.md) 및 [응용 프로그램 도메인 및 Visual c + +](../../dotnet/application-domains-and-visual-cpp.md)합니다.

## <a name="example"></a>예

다음 샘플에서는 C4398 오류가 발생 합니다.

```cpp
// C4398.cpp
// compile with: /clr /W3 /c
struct S {
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall
};

S glob_s;   // C4398
__declspec(appdomain) S glob_s2;   // OK
```