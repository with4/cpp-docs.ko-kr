---
title: 컴파일러 오류 C3223 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3223
dev_langs:
- C++
helpviewer_keywords:
- C3223
ms.assetid: 1f4380b4-0413-40db-a868-62f97babaf78
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b57ede45c2b7b2271f1f6d347f97f7d33334c13b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33250223"
---
# <a name="compiler-error-c3223"></a>컴파일러 오류 C3223
'property': 속성에 'typeid'를 적용할 수 없습니다.  
  
 속성에 [typeid](../../windows/typeid-cpp-component-extensions.md) 를 적용할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3223을 생성합니다.  
  
```  
// C3223.cpp  
// compile with: /clr  
ref class R {  
public:  
   property int myprop;  
};  
  
int main() {  
   System::Type^ type2 = R::myprop::typeid;   // C3223  
}  
```