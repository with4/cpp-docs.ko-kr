---
title: 컴파일러 경고 (수준 1) C4399 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4399
dev_langs:
- C++
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aedad6aed07a6056f74ad338037a7268c722627f
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34703722"
---
# <a name="compiler-warning-level-1-c4399"></a>컴파일러 경고(수준 1) C4399

> '*기호*': /clr으로 컴파일할 때 __declspec (dllimport)로 프로세스별 기호를 표시 하지 말아야: 순수

## <a name="remarks"></a>설명

**/clr: pure** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

순수 이미지에 네이티브 이미지 또는 기본 모드와 CLR 구문을 사용 하 여 이미지 데이터를 가져올 수 없습니다. 이 경고를 해결 하려면 사용 하 여 컴파일합니다. **/clr** (하지 **/clr: pure**) 또는 삭제 `__declspec(dllimport)`합니다.

## <a name="example"></a>예

다음 샘플에서는 C4399 오류가 발생 합니다.

```cpp
// C4399.cpp
// compile with: /clr:pure /doc /W1 /c
__declspec(dllimport) __declspec(process) extern const int i;   // C4399
```