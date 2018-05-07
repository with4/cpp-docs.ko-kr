---
title: 컴파일러 오류 C3072 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3072
dev_langs:
- C++
helpviewer_keywords:
- C3072
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6287ba8e84df96adb0447728dbde8f2031c986cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3072"></a>컴파일러 오류 C3072
'operator' 연산자는 ref 클래스의 인스턴스에 적용할 수 없습니다.  
  
 단항을 사용 하 여 '`operator` ' 연산자는 ref 클래스의 인스턴스를 핸들 형식으로 변환 하려면  
  
 CLR 형식 CLR 연산자, not 네이티브 (또는 표준) 연산자가 필요 합니다.  자세한 내용은 참조 [추적 참조 연산자](../../windows/tracking-reference-operator-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3072 오류가 발생 합니다.  
  
```  
// C3072.cpp  
// compile with: /clr  
ref class R {};  
  
int main() {  
   R r1;  
   R^ r2 = &r1;   // C3072  
   R^ r3 = %r1;   // OK  
}  
```