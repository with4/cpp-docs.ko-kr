---
title: "컴파일러 오류 C2011 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2011
dev_langs: C++
helpviewer_keywords: C2011
ms.assetid: 992c9d51-e850-4d53-b86b-02e73b38249c
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c599d6add1fa51c6aae7f04019eacdc94f11bb15
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2011"></a>컴파일러 오류 C2011
'identifier': 'type' 형식 재정의  
  
 식별자가 `type`으로 이미 정의되었습니다. 식별자 재정의를 확인하세요.  
  
 헤더 파일 또는 형식 라이브러리를 동일한 파일로 두 번 이상 가져오는 경우 C2011 오류가 발생할 수도 있습니다. 헤더 파일에 정의 된 형식의 여러 번 포함을 방지 하려면 사용 하 여 포함 가드 또는 `#pragma` [되 면](../../preprocessor/once.md) 헤더 파일에 지시문입니다.  
  
 를 다시 정의 된 형식의 초기 선언을 찾아야 해야 하는 경우 사용할 수 있습니다는 [/P](../../build/reference/p-preprocess-to-a-file.md) 컴파일러 플래그 전처리 된 출력을 생성 하는 컴파일러에 전달 합니다. 텍스트 검색 도구를 사용하여 출력 파일에서 다시 정의된 식별자의 인스턴스를 찾을 수 있습니다.  
  
 다음 샘플에서는 C2011 오류가 발생하는 경우 및 이를 해결하는 한 가지 방법을 보여 줍니다.  
  
```  
// C2011.cpp  
// compile with: /c  
struct S;  
union S;   // C2011  
union S2;   // OK  
```