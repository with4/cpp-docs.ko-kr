---
title: 컴파일러 경고 (수준 4) C4263 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4263
dev_langs:
- C++
helpviewer_keywords:
- C4263
ms.assetid: daabb05d-ab56-460f-ab6c-c74d222ef649
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 883b36e524f3631811cf503ebc695e3c4ad53da2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4263"></a>컴파일러 경고(수준 4) C4263
'function': 멤버 함수가 기본 클래스 가상 멤버 함수를 재정의 하지 않습니다  
  
 클래스 함수 정의 기본 클래스 하지만 하지 동일한 번호 또는 형식의 인수는 가상 함수 이름이 같은 합니다. 이 기본 클래스의 가상 함수와 효과적으로 숨깁니다.  
  
 기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.  
  
 다음 샘플에서는 C4263 오류가 생성 됩니다.  
  
```  
// C4263.cpp  
// compile with: /W4  
#pragma warning(default:4263)  
#pragma warning(default:4264)  
class B {  
public:  
   virtual void func();  
};  
  
class D : public B {  
   void func(int);   // C4263  
};  
  
int main() {  
}  
```