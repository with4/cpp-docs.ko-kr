---
title: "컴파일러 오류 C3908 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3908
dev_langs: C++
helpviewer_keywords: C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e3c364709704e5051bcfcb77777d15b18d46b375
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3908"></a>컴파일러 오류 C3908
'구문' 보다 덜 제한적인 액세스 수준  
  
 속성 접근자 메서드 (get 또는 set)는 자체 속성에 지정 된 보다 덜 제한적인 액세스 권한을 가질 수 없습니다.  경우에 마찬가지 이벤트 접근자 메서드  
  
 자세한 내용은 참조 [속성](../../windows/property-cpp-component-extensions.md) 및 [이벤트](../../windows/event-cpp-component-extensions.md)합니다.  
  
 다음 샘플에서는 C3908 오류가 생성 됩니다.  
  
```  
// C3908.cpp  
// compile with: /clr  
ref class X {  
protected:  
   property int i {  
   public:   // C3908 property i is protected   
      int get();  
   private:  
      void set(int);   // OK more restrictive  
   };  
};  
```