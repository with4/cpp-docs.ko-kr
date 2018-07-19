---
title: 컴파일러 오류 C2087 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2087
dev_langs:
- C++
helpviewer_keywords:
- C2087
ms.assetid: 89761e83-415a-4468-a4c6-b6dedfd1dd6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a6012bd49d9d68cbc3318afb390b5f5b411e39f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167111"
---
# <a name="compiler-error-c2087"></a>컴파일러 오류 C2087
'identifier': 첨자 누락  
  
 여러 첨자가 포함 된 배열 정의 하나 이상의 차원에 대 한 첨자 값이 없습니다.  
  
 다음 샘플에서는 C2087 오류가 생성 됩니다.  
  
```  
// C2087.cpp  
int main() {  
   char a[10][];   // C2087  
}  
```  
  
 해결 방법:  
  
```  
// C2087b.cpp  
int main() {  
   char b[4][5];  
}  
```