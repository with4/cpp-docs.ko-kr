---
title: 유령 | Microsoft Docs
ms.custom: ''
ms.date: 1/23/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- spectre_cpp
- spectre
- nomitigation
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword (C++), spectre
- spectre __declspec keyword
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 153ff690b975ecb442c260fcebce73acd32d03fb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32422412"
---
# <a name="spectre"></a>유령

**Microsoft 전용**

유령 variant 1 잘못 된 장벽 명령을 실행 하는 함수에 대 한 삽입 하지 않도록 컴파일러에 지시 합니다.

## <a name="syntax"></a>구문

> **__declspec (spectre(nomitigation))**  

## <a name="remarks"></a>설명

[/Qspectre](../build/reference/qspectre.md) 컴파일러 옵션을 사용 하면 분석 결과 유령 variant 1 보안 취약점을 발생 하는 여기서 추론 실행 장벽 지침을 삽입 하도록 컴파일러에 있습니다. 내보낸 특정 명령 프로세서에 따라 달라 집니다. 이러한 지침은 코드 크기나 성능에 미치는 영향을 최소화 해야 보유 하 고, 코드는 보안 문제에 영향을 받지 않습니다 있고 최대 성능이 필요한 경우도 있을 수 있습니다.

전문가 분석 함수 유령 variant 1 범위 검사 바이패스 결함 으로부터 안전한 지 확인할 수 있습니다. 적용 하 여 함수 내에서 완화 코드 생성을 방지할 수는 경우 `__declspec(spectre(nomitigation))` 함수 선언에 있습니다.

> [!CAUTION]
> **/Qspectre** 추론 실행 장벽 지침 중요 한 보안 기능을 제공 하 고 성능에 거의 영향을 줄 합니다. 함수의 성능이 매우 중요하고 해당 함수의 안전성이 파악되는 드문 경우를 제외하고, 버퍼 보안 검사를 억제하지 않도록 권장합니다.

## <a name="example"></a>예제

다음 코드를 사용 하는 방법을 보여 줍니다 `__declspec(spectre(nomitigation))`합니다.

```cpp
// compile with: /c /Qspectre
static __declspec(spectre(nomitigation))
int noSpectreIssues() {
    // No Spectre variant 1 vulnerability here
    // ...
    return 0;
}

int main() {
    noSpectreIssues();
    return 0;
}
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[__declspec](../cpp/declspec.md)  
[키워드](../cpp/keywords-cpp.md)  
[/Qspectre](../build/reference/qspectre.md)  
