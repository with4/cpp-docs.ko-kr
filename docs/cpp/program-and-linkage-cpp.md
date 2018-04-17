---
title: 프로그램 및 링크 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 04/09/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: a6493ba0-24e2-4c89-956e-9da1dea660cb
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab24c552a150e5a14037d727c8d3428eb6bbf809
ms.sourcegitcommit: 770f6c4a57200aaa9e8ac6e08a3631a4b4bdca05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="program-and-linkage--c"></a>프로그램 및 링크 (c + +)

C + + 프로그램에서 각 전역 기호 정의할 수 있습니다를 한 번만 프로그램 여러 변환 단위 구성 된 경우에 합니다. 변환 단위는 구현 파일 (.cpp,.hpp,.cxx 등)와 직접 또는 간접적으로 포함 하는 모든 헤더 구성 됩니다. 프로그램은 함께 연결된 하나 이상의 변환 단위로 구성됩니다. 

## <a name="linkage-vs-scope"></a>범위 및 링크

개념 *링크* 변환 단위 간에 전체 프로그램 내에서 전역 기호 (예: 변수, 형식 이름 및 함수 이름)의 표시 유형을 참조 합니다. 개념 *범위* 네임 스페이스, 클래스 또는 함수 본문 같은 블록 내에 선언 된 기호를 가리킵니다. 이러한 기호는 정의 된; 범위 내 에서만 표시 됩니다. 링크의 개념에 적용 되지 않습니다.

## <a name="external-vs-internal-linkage"></a>내부 링크 및 외부

비 const 전역 변수 및 기본적으로 사용 가능한 함수는 외부 링크가 있습니다. 프로그램에 모든 변환 단위에서 표시 됩니다. 명시적으로 선언 하 여이 동작을 재정의할 수 **정적** 선언 된 동일한 번역 단위에 해당 표시 여부를 제한 하는 합니다. 이 의미 **정적** 지역 변수에 적용할 때 해당 의미와 다릅니다. 로 선언 된 변수 **const** 기본적으로는 내부 링크를 사용 합니다.

## <a name="extern-constexpr-linkage"></a>Extern constexpr 링크

이전 버전의 Visual Studio에서는 컴파일러 항상 겠지만 constexpr 변수 내부 링크가 변수 extern으로 표시 된 경우에 합니다. Visual Studio 2017 15.5 버전에서 새 컴파일러 스위치(/Zc:externConstexpr)는 올바른 표준 준수 동작을 활성화합니다. 결국 이는 기본값이 됩니다.

```cpp
extern constexpr int x = 10; //error LNK2005: "int const x" already defined
```

표시 되어야 하는 데 필요한 헤더 파일에 선언 된 변수 extern constexpr이 있으면 **__declspec (selectany)** 올바르게 결합 해당 중복 선언 하려면:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

## <a name="see-also"></a>참고 항목

 [기본 개념](../cpp/basic-concepts-cpp.md)