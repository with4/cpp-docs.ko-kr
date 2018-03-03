---
title: "/Zc:externConstexpr (enable extern constexpr 변수) | Microsoft Docs"
ms.custom: 
ms.date: 9/29/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /Zc:externConstexpr
dev_langs:
- C++
helpviewer_keywords:
- -Zc:externConstexpr compiler option (C++)
- extern constexpr variables (C++)
ms.assetid: 4da5e33a-2e4d-4ed2-8616-bd8f43265c27
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 84037e5e8a942d51175d97957d0c05bd6f4aa29d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="zcexternconstexpr-enable-extern-constexpr-variables"></a>/Zc:externConstexpr (extern constexpr 변수 사용)

**/Zc:externConstexpr** 컴파일러 옵션에 대 한 외부 링크를 허용 하 고 c + + 표준을 준수 하도록 컴파일러에 지시 `constexpr` 변수입니다. 기본적으로 Visual Studio 항상 제공 된 `constexpr` 지정 하는 경우에 변수 내부 링크-는 `extern` 키워드입니다.

## <a name="syntax"></a>구문

> /Zc:externConstexpr [-]

## <a name="remarks"></a>설명

**/Zc:externConstexpr** 컴파일러 옵션을 사용 하면 외부 링크를 사용 하 여 선언 된 변수를 적용할 컴파일러 `extern constexpr`합니다. **/Zc:externConstexpr** 옵션은 Visual Studio 2017 업데이트 15.5부터 사용할 수 있습니다. 이전 버전의 Visual Studio 및 기본적으로 또는 **/Zc:externConstexpr-** Visual Studio 적용에 내부 링크가 지정 된 `constexpr` 경우라도 변수는 `extern` 키워드를 사용 합니다.

헤더 파일에 선언 된 변수에 포함 되어 있으면 `extern constexpr`를 표시 해야 [__declspec (selectany)](../../cpp/selectany.md) 중복 선언 된 연결 된 이진 파일에서 단일 인스턴스에 병합 하려면. 그렇지 않으면 단일 정의 규칙의 위반에 대 한 LNK2005 예를 들어, 링커 오류가 표시 될 수 있습니다.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Visual Studio에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 아래 **구성 속성**를 확장 하 고 **C/c + +** 선택한 후 **명령줄**합니다.

1. 추가 **/Zc:externConstexpr** 또는 **/Zc:externConstexpr-** 에 **추가 옵션:** 창.

## <a name="see-also"></a>참고 항목

[/Zc (규칙)](../../build/reference/zc-conformance.md)  
[auto 키워드](../../cpp/auto-keyword.md)