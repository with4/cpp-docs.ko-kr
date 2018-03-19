---
title: "함수 본문 | Microsoft Docs"
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
- functions [C], syntax
- variables, function syntax
- function definitions, function body
- function body
ms.assetid: f7e74822-fac8-4dc8-8f3a-2b1611da4640
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a0c85ecf0752ff34bf5b61e42309360f2bc4d448
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2018
---
# <a name="function-body"></a>함수 본문
"함수 본문"은 함수가 수행하는 작업을 지정하는 문이 포함된 복합 문입니다.  
  
## <a name="syntax"></a>구문  
 *function-definition*:  
 *declaration-specifiers* opt*attribute-seq* opt*declarator declaration-list* opt*compound-statement*  
  
 /\* *attribute-seq*는 Microsoft 전용임 \*/  
  
 *compound-statement*: /\* 함수 본문 \*/  
 **{**  *declaration-list* opt*statement-list* opt**}**  
  
 함수 본문에 선언된 변수인 "지역 변수"에는 다르게 지정되지 않는 한 **auto** 저장소 클래스가 있습니다. 함수가 호출되면 지역 변수에 대한 저장소가 만들어지고 로컬 초기화가 수행됩니다. 실행 제어는 *compound-statement*의 첫 번째 문으로 전달되고 `return` 문이 실행되거나 함수 본문 끝에 도달할 때까지 계속됩니다. 그런 다음 함수가 호출된 지점으로 제어가 반환됩니다.  
  
 함수가 값을 반환할 경우 식을 포함하는 `return` 문이 실행되어야 합니다. 함수의 반환 값은 `return` 문이 실행되지 않거나 `return` 문에 식이 포함되지 않은 경우 정의되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C 함수 정의](../c-language/c-function-definitions.md)