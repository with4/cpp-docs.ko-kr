---
title: "컴파일러 오류 C2026 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2026
dev_langs:
- C++
helpviewer_keywords:
- C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: c429f81c64b7710b7edc2b8540d98e8c790e4062
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2026"></a>컴파일러 오류 C2026
문자열이 너무 길어 뒤에 오는 문자가 잘립니다.  
  
 문자열 16380 단일 바이트 문자 제한을 초과 했습니다.  
  
 인접 문자열을 연결 하기 전에 문자열 16380 단일 바이트 문자 보다 길 수 없습니다.  
  
 이 길이 절반의 유니코드 문자열에는이 오류가 발생도 합니다.  
  
 다음과 같이 정의 하는 문자열에 있으면 C2026 발생 합니다.  
  
```  
char sz[] =  
"\  
imagine a really, really \  
long string here\  
";  
```  
  
 구분 하면 것 다음과 같이 합니다.  
  
```  
char sz[] =  
"\  
imagine a really, really "  
"long string here\  
";  
```  
  
 수 저장 하려는 매우 큰 문자열 리터럴 (32 K 이상) 사용자 지정 리소스 또는 외부 파일에 있습니다. 참조 [새 사용자 지정 또는 데이터 리소스 만들기](../../windows/creating-a-new-custom-or-data-resource.md) 에 대 한 자세한 내용은 합니다.
