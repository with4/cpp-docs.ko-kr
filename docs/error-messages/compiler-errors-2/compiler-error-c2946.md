---
title: "컴파일러 오류 C2946 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2946
dev_langs:
- C++
helpviewer_keywords:
- C2946
ms.assetid: c86dfbfc-7702-4f09-8a53-d205710e99c2
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 151d69bc17ea52b0c6968933b3a50112c7800d2c
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2946"></a>컴파일러 오류 C2946
명시적 인스턴스화. 'class'는 템플릿-클래스 특수화가 아닙니다.  
  
 템플릿이 아닌 클래스를 명시적으로 인스턴스화할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2946을 생성합니다.  
  
```  
// C2946.cpp  
class C {};  
template C;  // C2946  
int main() {}  
```
