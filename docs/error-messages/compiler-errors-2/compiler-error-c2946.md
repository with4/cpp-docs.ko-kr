---
title: "컴파일러 오류 C2946 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2946
dev_langs: C++
helpviewer_keywords: C2946
ms.assetid: c86dfbfc-7702-4f09-8a53-d205710e99c2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e5e02ea2e96a3c6356a9372700c80d000aa48992
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2946"></a>컴파일러 오류 C2946
명시적 인스턴스화. 'class'는 템플릿-클래스 특수화가 아닙니다.  
  
 템플릿이 아닌 클래스를 명시적으로 인스턴스화할 수 없습니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C2946을 생성합니다.  
  
```  
// C2946.cpp  
class C {};  
template C;  // C2946  
int main() {}  
```