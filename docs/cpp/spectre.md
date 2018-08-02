---
title: 스펙터 | Microsoft Docs
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
ms.openlocfilehash: a51d47764ea4515fcbc2cb3b7aa37fd341cd130e
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463231"
---
# <a name="spectre"></a>스펙터

**Microsoft 전용**

함수에 대 한 Spectre variant 1 투기적 실행 장벽 지침을 삽입 하지 않도록 컴파일러에 알려 줍니다.

## <a name="syntax"></a>구문

> **__declspec (spectre(nomitigation))**  

## <a name="remarks"></a>설명

합니다 [/Qspectre](../build/reference/qspectre.md) 컴파일러 옵션을 사용 하면 여기서 analysis Spectre 변형 1 취약성을 있는지 나타냅니다 투기적 실행 장벽 지침을 삽입 하도록 컴파일러에 있습니다. 내보낸 특정 명령 프로세서에 따라 달라 집니다. 이러한 지침은 코드 크기 또는 성능에 미치는 영향을 최소화가 해야 하는 동안 코드의 취약점으로 인 한 영향을 받지 대 한 최대 성능이 필요한 경우 있을 수 있습니다.

전문가 분석 함수 Spectre 변형 1 범위 확인 사용 안 함 오류 로부터 안전 하 게 임을 확인할 수 있습니다. 이 경우 적용 하 여 함수 내에서 완화 코드의 생성을 무시할 수 있습니다 `__declspec(spectre(nomitigation))` 함수 선언에 있습니다.

> [!CAUTION]
> 합니다 **/Qspectre** 투기적 실행 장벽 지침 중요 한 보안 보호 제공 하며 성능에는 거의 영향을 주지 합니다. 함수의 성능이 매우 중요하고 해당 함수의 안전성이 파악되는 드문 경우를 제외하고, 버퍼 보안 검사를 억제하지 않도록 권장합니다.

## <a name="example"></a>예

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
