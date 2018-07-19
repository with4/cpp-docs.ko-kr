---
title: 컴파일러 오류 C2026 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2026
dev_langs:
- C++
helpviewer_keywords:
- C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6b2952daa8cc7b3642cca5ba278990fde7d1ebe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167667"
---
# <a name="compiler-error-c2026"></a>컴파일러 오류 C2026
문자열이 너무 길어 잘립니다. 후행 문자  
  
 문자열 16380 단일 바이트 문자 제한을 초과 했습니다.  
  
 인접 문자열을 연결 하기 전에 문자열로 16380 단일 바이트 문자 보다 길 수 없습니다.  
  
 절반이 길이의 유니코드 문자열에이 오류가 발생도 합니다.  
  
 다음과 같이 정의 하는 문자열에 있으면 C2026 발생 합니다.  
  
```  
char sz[] =  
"\  
imagine a really, really \  
long string here\  
";  
```  
  
 있습니다 수 나누십시오 다음과 같습니다.  
  
```  
char sz[] =  
"\  
imagine a really, really "  
"long string here\  
";  
```  
  
 사용자 지정 리소스 또는 외부 파일에 매우 큰 문자열 리터럴 (32 K 이상)를 저장할 만한 합니다. 참조 [새 사용자 지정 또는 데이터 리소스 만들기](../../windows/creating-a-new-custom-or-data-resource.md) 자세한 정보에 대 한 합니다.