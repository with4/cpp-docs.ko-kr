---
title: "심각한 오류 C1383 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1383
dev_langs:
- C++
helpviewer_keywords:
- C1383
ms.assetid: ca224d14-d687-4fd6-80c2-8b82f28924ea
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: bbd890a7506059f939ca6d8957f71e20cba771f8
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1383"></a>심각한 오류 C1383
컴파일러 옵션 /GL은 설치된 공용 언어 런타임 버전과 호환되지 않습니다.  
  
 최신 컴파일러에서 이전 버전의 공용 언어 런타임을 사용하며 **/clr** 및 **/GL.**으로 컴파일하는 경우 C1383이 발생합니다.  
  
 해결하려면 **/clr** 과 함께 **/GL** 을 사용하지 않거나, 컴파일러와 함께 제공된 공용 언어 런타임 버전을 설치합니다.  
  
 자세한 내용은 참조 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 및 [/GL (전체 프로그램 최적화)](../../build/reference/gl-whole-program-optimization.md)합니다.
