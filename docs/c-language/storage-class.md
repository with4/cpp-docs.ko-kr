---
title: "저장소 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- linkage [C++], external
- function storage class
- function specifiers, storage class
- storage classes
- Microsoft-specific storage classes
- external linkage, storage-class specifiers
- static storage class specifiers
ms.assetid: 39a79ba6-edf5-42b6-8e45-f94227603dd6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4385515becbb32b256b2bf6562af941371ef47e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="storage-class"></a>저장소 클래스
함수 정의의 저장소 클래스 지정자는 함수에 `extern` 또는 **static** 저장소 클래스를 제공합니다.  
  
## <a name="syntax"></a>구문  
 *function-definition*:  
 *declaration-specifiers* opt*attribute-seq* opt*declarator declaration-list* opt*compound-statement*  
  
 /\* *attribute-seq*는 Microsoft 전용임 */  
  
 *declaration-specifiers*:  
 *storage-class-specifier declaration-specifiers* opt  
  
 *type-specifier declaration-specifiers* opt  
  
 *type-qualifier declaration-specifiers* opt  
  
 *storage-class-specifier*: /\* 함수 정의용 \*/  
 **extern**  
  
 **static**  
  
 함수 정의에 *storage-class-specifier*가 포함되지 않은 경우 저장소 클래스의 기본값은 `extern`입니다. 함수를 명시적으로 `extern`으로 선언할 수 있지만 반드시 그렇게 할 필요는 없습니다.  
  
 함수 선언에 *storage-class-specifier* `extern`이 포함되어 있는 경우 식별자의 링크가 파일 범위를 포함하는 식별자의 모든 표시되는 선언의 링크와 동일합니다. 파일 범위를 포함하는 표시되는 선언이 없는 경우 식별자에 외부 링크가 있습니다. 식별자에 파일 범위가 있으며 *storage-class-specifier*는 없는 경우 식별자에 외부 링크가 있습니다. 외부 링크는 식별자의 각 인스턴스가 동일한 개체 또는 함수를 표시함을 의미합니다. 링크 및 파일 범위에 대한 자세한 내용은 [수명, 범위, 표시 유형 및 링크](../c-language/lifetime-scope-visibility-and-linkage.md)를 참조하세요.  
  
 `extern`이 아닌 저장소 클래스 지정자를 포함하는 블록 범위 함수 선언은 오류를 발생시킵니다.  
  
 **static** 저장소 클래스를 포함하는 함수는 정의된 소스 파일에서만 볼 수 있습니다. 다른 모든 함수는 `extern` 저장소 클래스가 명시적으로 또는 암시적으로 제공된 경우 프로그램의 모든 소스 파일에서 표시됩니다. **static** 저장소 클래스가 필요한 경우 함수가 처음으로 선언된 경우 및 함수가 정의된 경우 선언되어야 합니다.  
  
 **Microsoft 전용**  
  
 Microsoft 확장을 사용할 수 있을 때 함수 정의가 동일한 소스 파일에 있는 경우 및 정의가 명시적으로 **static** 저장소 클래스를 지정하는 경우 원래 저장소 클래스를 사용하지 않거나 `extern` 저장소 클래스를 사용하여 선언된 함수에 **static** 저장소 클래스가 지정됩니다.  
  
 /Ze 컴파일러 옵션을 사용하여 컴파일할 때 `extern` 키워드를 사용하여 블록 내에서 선언된 함수가 전역으로 표시됩니다. /Za를 사용하여 컴파일할 때에는 이것이 적용되지 않습니다. 이 기능은 소스 코드의 이식성을 고려해야 하는 경우 사용할 수 없습니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [C 함수 정의](../c-language/c-function-definitions.md)