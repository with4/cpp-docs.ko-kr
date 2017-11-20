---
title: "컴파일러 경고 (수준 4) C4202 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4202
dev_langs: C++
helpviewer_keywords: C4202
ms.assetid: 253293aa-97a3-4878-a2e8-c6cc9e20b1cb
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d23d417b89f2b810fcf78c141bd51eb7ef4b311d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4202"></a>컴파일러 경고(수준 4) C4202
비표준 확장이 사용 됨: '...': 프로토타입 매개 변수가 이름 목록이 잘못 되었습니다  
  
 이전 스타일 함수 정의는 가변 인수가 포함 되어 있습니다. ANSI 규격 오류를 생성 하는 이러한 정의 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).  
  
## <a name="example"></a>예제  
  
```  
// C4202.c  
// compile with: /W4  
void func( a, b, ...)   // C4202  
int a, b;  
{}  
  
int main()  
{  
}  
```