---
title: '#줄 지시문 (C/c + +) | Microsoft Docs'
ms.custom: ''
ms.date: 10/18/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#line'
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, directives
- line directive (#line)
- '#line directive'
ms.assetid: 585c1dc4-5184-4f01-98f4-80c1909744d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ebbcea7432b27e9269b5041d90d14534a77b812
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33839756"
---
# <a name="line-directive-cc"></a>#line 지시문 (C/C++)

`#line` 지시문에는 지정 된 줄 번호 및 파일 이름에는 컴파일러의 내부적으로 저장 된 줄 번호와 파일 이름을 변경 하도록 전처리기에 지시 합니다.

## <a name="syntax"></a>구문

> **#line** *자리 시퀀스* ["*filename*"]

## <a name="remarks"></a>설명

컴파일러 줄 번호 및 선택적인 파일 이름을 사용 하 여 컴파일하는 동안 발견 된 오류를 참조 합니다. 현재 입력된 파일을 파일 이름 참조 및 줄 번호는 일반적으로 현재 입력된 행을 말합니다. 줄 번호는 각 줄에서 처리 된 후에 증가 됩니다.

*자리 시퀀스* 값 정수 상수를 사용할 수 있습니다. 전처리 토큰에서 매크로 대체를 수행할 수 있지만 결과 올바른 구문으로 계산 되어야 합니다. *filename* 문자의 조합이 포함 될 수 하 고 큰따옴표로 묶어야 합니다 (**""**). 경우 *filename* 은 생략 하면 이전 파일 이름 변경 되지 않습니다.

작성 하 여 소스 줄 번호와 파일 이름을 변경할 수는 `#line` 지시문입니다. 변환기의 줄 번호 및 파일 이름을 사용 하 여 미리 정의 된 매크로의 값을 확인 하려면 **&#95; &#95;파일&#95; &#95;** 및 **&#95; &#95;줄&#95; &#95;**. 프로그램 텍스트에 이름은 오류 메시지를 삽입할 이러한 매크로 사용할 수 있습니다. 이러한 미리 정의 된 매크로에 대 한 자세한 내용은 참조 하십시오. [미리 정의 된 매크로](../preprocessor/predefined-macros.md)합니다.

**&#95; &#95;파일&#95; &#95;** 매크로 문자열 확장 내용이 큰따옴표로 묶은 파일 이름 (**""**).

줄 번호와 파일 이름을 변경 하면 컴파일러는 이전 값을 무시 하 고 새 값으로 처리를 계속 됩니다. `#line` 지시문은 일반적으로 오류 메시지를 생성 된 프로그램을 대신 원래 소스 파일을 참조 하기 때문에 프로그램 생성기에서 사용 됩니다.

다음 예제는 설명 `#line` 및 **&#95; &#95;줄&#95; &#95;** 및 **&#95; &#95;파일&#95; &#95;** 매크로입니다.

이 문에서 내부적으로 저장 된 줄 번호를 151로 설정 하 고 파일 이름을 copy.c로 변경 됩니다.

```cpp
#line 151 "copy.c"
```

 이 예제에서는 매크로 `ASSERT` 미리 정의 된 매크로 사용 하 여 **&#95; &#95;줄&#95; &#95;** 및 **&#95; &#95;파일&#95; &#95;** 인쇄 하는 지정 된 어설션 true가 아니면 소스 파일에 대 한 오류 메시지입니다.

```cpp
#define ASSERT(cond) if( !(cond) )\
{printf( "assertion error line %d, file(%s)\n", \
__LINE__, __FILE__ );}
```

## <a name="see-also"></a>참고 항목

[전처리기 지시문](../preprocessor/preprocessor-directives.md)