---
title: "컴파일러 오류 C3284 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3824
dev_langs: C++
helpviewer_keywords: C3284
ms.assetid: e582f316-e9db-4d27-9c70-fdfa737a9d5f
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9ec3f536b17a2cc8ec180d87270b85938e9a9637
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3284"></a>컴파일러 오류 C3284
'function' 함수의 'parameter' 제네릭 매개 변수에 대한 제약 조건은 'function' 함수의 제네릭 매개 변수 'parameter'의 제약 조건과 일치해야 합니다.  
  
 가상 제네릭 함수는 기본 클래스에서 동일한 이름 및 인수 집합을 갖는 가상 함수와 동일한 제약 조건을 사용해야 합니다.  
  
 다음 샘플에서는 C3284를 생성합니다.  
  
```  
// C3284.cpp  
// compile with: /clr /c  
// C3284 expected  
public interface class IGettable {  
   int Get();  
};  
  
public interface class B {  
   generic<typename T>  
   where T : IGettable  
   virtual int mf(T t);  
};  
  
public ref class D : public B {  
public:  
   generic<typename T>  
   // Uncomment the following line to resolve.  
   // where T : IGettable  
   virtual int mf(T t) {  
      return 4;  
   }  
};  
```