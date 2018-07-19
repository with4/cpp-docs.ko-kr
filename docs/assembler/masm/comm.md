---
title: 통신 | Microsoft Docs
ms.custom: ''
ms.date: 05/22/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- COMM
dev_langs:
- C++
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1df6c729ab130a7ff38d7f7cf83224e7425e7dba
ms.sourcegitcommit: da7b7533d1a4dc141cc0f09149e4e4196f2fe329
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34463025"
---
# <a name="comm"></a>COMM

에 지정 된 특성을 가진 공용 변수를 만듭니다 *정의*합니다.

## <a name="syntax"></a>구문

> **통신** *정의* [, *정의*]...

## <a name="remarks"></a>설명

공용 변수는 링커로 할당 되 고 초기화할 수 없습니다. 즉, 위치 또는 이러한 변수는 시퀀스에는 종속 될 수 없습니다.

각 *정의* 형식은 다음과 같습니다.

[*langtype*] [**NEAR** &#124; **원거리**] _레이블_**:**_형식_[**:**_count_]

선택적 *langtype* 뒤에 오는 이름이 대 한 명명 규칙을 설정 합니다. 지정 된 모든 언어 재정의 **합니다. 모델** 지시문입니다. 선택적 **NEAR** 또는 **원거리** 현재 메모리 내 모델을 재정의 합니다. *레이블* 변수의 이름입니다. *형식* 형식 지정자를 사용할 수 있습니다 ([바이트](../../assembler/masm/byte-masm.md), [단어](../../assembler/masm/word.md)등) 또는 바이트 수를 지정 하는 정수입니다. 선택적 *count* 선언 된 데이터 개체;의 요소 수를 지정 합니다. 기본값은 1입니다.

## <a name="example"></a>예제

이 예제에서는 512 바이트 요소의 배열을 만듭니다.

```masm
COMM FAR ByteArray:BYTE:512
```

## <a name="see-also"></a>참고자료

[지시문 참조](../../assembler/masm/directives-reference.md)
