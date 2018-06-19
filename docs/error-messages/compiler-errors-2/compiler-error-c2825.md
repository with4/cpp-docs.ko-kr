---
title: 컴파일러 오류 C2825 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2825
dev_langs:
- C++
helpviewer_keywords:
- C2825
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5352901d50e011229ed9aa4715923881c26a8fe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33237239"
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