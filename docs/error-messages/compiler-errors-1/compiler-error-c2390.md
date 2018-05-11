---
title: 컴파일러 오류 C2390 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2390
dev_langs:
- C++
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a32a9ca77ba43e5f2866baed91b99103224dbc0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2390"></a>컴파일러 오류 C2390
'identifier': 저장소 클래스가 잘못 되었습니다 'specifier'  
  
 저장소 클래스는 전역 범위 식별자에 대해 올바르지 않습니다. 기본 저장소 클래스가 잘못 되었습니다. 클래스 대신 사용 됩니다.  
  
 가능한 해결 방법:  
  
-   식별자가 함수를 사용 하 여 선언 `extern` 저장 합니다.  
  
-   지역 변수 또는 형식 매개 변수 식별자 이면 자동 저장소로 선언 합니다.  
  
-   식별자는 전역 변수, 저장소 클래스 (자동 저장소) 없이 선언 합니다.  
  
## <a name="example"></a>예제  
  
-   다음 샘플에서는 C2390 오류가 생성 됩니다.  
  
```  
// C2390.cpp  
register int i;   // C2390  
  
int main() {  
   register int j;   // OK  
}  
```