---
title: "컴파일러 오류 C2825 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2825
dev_langs: C++
helpviewer_keywords: C2825
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ebe700fed581eadbab256c9c4f9e2f71bf1d1585
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2825"></a>컴파일러 오류 C2825
var: 클래스 또는 네임 스페이스 뒤에 나올 여야 ':: '  
  
 정규화 된 이름을 만드는 데 실패 한 시도가.  
  
 예를 들어 코드에서 함수 이름을로 시작 하는 함수 선언에 포함 되지 않습니다 있는지를 확인:: 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2825 오류가 생성 됩니다.  
  
```  
// C2825.cpp  
typedef int i;  
int main() {  
   int* p = new int;  
   p->i::i();   // C2825  
   // try the following line instead  
   // p->i::~i();  
}  
```