---
title: "#ifdef 및 #ifndef 지시문 (C/c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- '#ifndef'
- '#ifdef'
dev_langs:
- C++
helpviewer_keywords:
- '#ifdef directive'
- preprocessor, directives
- ifdef directive (#ifdef)
- ifndef directive (#ifndef)
- '#ifndef directive'
ms.assetid: 2b0be69d-9e72-45d8-8e24-e4130fb2455b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a8f1a10e9d8437b71591efc9ce2915c9f485e0c4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="ifdef-and-ifndef-directives-cc"></a>#ifdef 및 #ifndef 지시문 (C/C++)
**#ifdef** 및 **#ifndef** 으로 동일한 작업을 수행 하는 지시문은 `#if` 지시문을 함께 사용할 경우 **정의**( *식별자* ).  
  
## <a name="syntax"></a>구문  
  
```  
#ifdef identifier  
#ifndef identifier  
  
// equivalent to  
#if defined identifier  
#if !defined identifier  
```  
  
## <a name="remarks"></a>설명  
 사용할 수는 **#ifdef** 및 **#ifndef** 지시문 아무 곳 이나 `#if` 사용할 수 있습니다. **#ifdef** *식별자* 문을 같습니다 `#if 1` 때 *식별자* 를 정의한와 동일 `#if 0` 때 *식별자* 정의 되지 않았습니다.으로 정의 된 또는 `#undef` 지시문입니다. 이러한 지시문은 C 또는 C++ 소스 코드에서 선언된 식별자가 아니라 `#define`으로 정의된 식별자가 있는지 여부만 검사합니다.  
  
 이러한 지시문은 이전 버전 언어와의 호환성을 위해서만 제공됩니다. **정의 (** *식별자* **)** 함께 사용 하는 상수 식에서 `#if` 지시문은 것이 좋습니다.  
  
 **#ifndef** 지시문에서 확인 하는 조건의 반대 조건을 확인 **#ifdef**합니다. 식별자가 정의되지 않았거나 해당 정의가 `#undef`를 통해 제거된 경우 조건은 true(0이 아닌 값)입니다. 그렇지 않으면 조건은 false(0)입니다.  
  
 **Microsoft 전용**  
  
 *식별자* /D 옵션을 사용 하 여 명령줄에서 전달 될 수 있습니다. /D로 최대 30개의 매크로를 지정할 수 있습니다.  
  
 정의는 명령줄에서 전달될 수 있으므로 정의가 존재하는지 여부를 확인하는 데 유용합니다. 예:  
  
```  
// ifdef_ifndef.CPP  
// compile with: /Dtest /c  
#ifndef test  
#define final  
#endif  
```  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [전처리기 지시문](../preprocessor/preprocessor-directives.md)