---
title: "-Zc (규칙) | Microsoft Docs"
ms.custom: 
ms.date: 9/29/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /zc
dev_langs: C++
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 86b12604a5348c3a1aabb33c7e13a4e7a3c57932
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="zc-conformance"></a>/Zc(규칙)

사용할 수는 **/Zc** 컴파일러 옵션을 표준 또는 Microsoft 전용 컴파일러 동작을 지정 합니다.

## <a name="syntax"></a>구문

> / Zc:_옵션_{,_옵션_}

## <a name="remarks"></a>설명

Visual Studio에서 C 또는 c + + 표준과 호환 되지 않는 확장 문제를 사용할 수 있습니다는 `/Zc` 표준 준수 또는 Microsoft 특정 동작을 지정 하는 규칙 옵션입니다. 일부 옵션 Microsoft 전용 동작이 대규모 주요 변경 내용이 기존 코드를 방지 하기 위해 기본값입니다. 다른 경우에는 기본값이 표준 동작 보안, 성능 또는 호환성의 향상 된 비용을 주요 변경 내용을 능가 하는 위치입니다. 최신 버전의 Visual Studio에서 각 규칙에 따라 옵션의 기본 설정은 변경할 수 있습니다. 각 규칙에 따라 옵션에 대 한 자세한 내용은 특정 옵션에 대 한 항목을 참조 합니다.

이들은 `/Zc` 컴파일러 옵션:

|옵션|동작|
|---|---|
|[alignedNew\[-\]](zc-alignednew.md)|C + + 17 과잉 맞춤된 동적 할당을 사용 하도록 설정 (에 기본적으로 C + +에서 17).|
|[자동\[-\]](zc-auto-deduce-variable-type.md)|에 대 한 새 표준 c + + 의미 적용 `auto` (에 기본적으로).|
|[externConstexpr\[-\]](zc-externconstexpr.md)|에 대 한 외부 링크를 사용 하도록 설정 `constexpr` 변수 (기본적으로 해제) 합니다.|
|[forScope\[-\]](zc-forscope-force-conformance-in-for-loop-scope.md)|표준 c + + 적용 `for` 범위 지정 규칙 (에 기본적으로).|
|[implicitNoexcept\[-\]](zc-implicitnoexcept-implicit-exception-specifiers.md)|암시적 사용 `noexcept` 에 필요한 기능 (에 기본적으로).|
|[인라인\[-\]](zc-inline-remove-unreferenced-comdat.md)|COMDAT 이거나 내부 링크만 경우 참조 되지 않은 함수 또는 데이터 제거 (기본적으로 해제) 합니다.|
|[noexceptTypes\[-\]](zc-noexcepttypes.md)|C + + 17 noexcept 규칙 적용 (에 기본적으로 C + + 17에 또는 나중에).|
|[referenceBinding\[-\]](zc-referencebinding-enforce-reference-binding-rules.md)|UDT 임시 비 const lvalue 참조에 바인딩되지 것입니다 (기본적으로 해제) 합니다.|
|[rvalueCast\[-\]](zc-rvaluecast-enforce-type-conversion-rules.md)|표준 c + + 명시적 형식 변환 규칙 적용 (기본적으로 해제) 합니다.|
|[sizedDealloc\[-\]](zc-sizeddealloc-enable-global-sized-dealloc-functions.md)|C + + 14 전역 크기 지정 된 할당 해제 함수를 사용 하도록 설정 (에 기본적으로).|
|[strictStrings\[-\]](zc-strictstrings-disable-string-literal-type-conversion.md)|문자열 리터럴 사용 안 함 `char*` 또는 `wchar_t*` 변환 (기본적으로 해제) 합니다.|
|[threadSafeInit\[-\]](zc-threadsafeinit-thread-safe-local-static-initialization.md)|스레드로부터 안전한 로컬 정적 초기화를 사용 하도록 설정 (에 기본적으로).|
|[throwingNew\[-\]](zc-throwingnew-assume-operator-new-throws.md)|가정 `operator new` 실패 시 throw (기본적으로 해제) 합니다.|
|[삼중 자\[-\]](zc-trigraphs-trigraphs-substitution.md)|삼중 자 (사용 되지 않음, off 기본적으로)을 사용 하도록 설정 합니다.|
|[wchar_t\[-\]](zc-wchar-t-wchar-t-is-native-type.md)|`wchar_t`네이티브 형식이 아닙니다 (에 기본적으로).|

Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[컴파일러 옵션](compiler-options.md)  
[컴파일러 옵션 설정](setting-compiler-options.md)
