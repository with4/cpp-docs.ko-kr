---
title: "컴파일러 오류 C3831 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3831"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3831"
ms.assetid: a125d8dc-b75a-4ea0-b6c7-fe7b119dba25
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3831
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member': 'class'에는 고정된 데이터 멤버 또는 고정 포인터를 반환하는 멤버 함수를 사용할 수 없습니다.  
  
 [pin\_ptr \(C\+\+\/CLI\)](../../windows/pin-ptr-cpp-cli.md) 또는 [\_\_pin](../../misc/pin.md)이 잘못 사용되었습니다.  
  
 다음 샘플에서는 C3831 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3831a.cpp  
// compile with: /clr  
ref class Y  
{  
public:  
   int i;  
};  
  
ref class X  
{  
   pin_ptr<int> mbr_Y;   // C3831  
   int^ mbr_Y2;   // OK  
};  
  
int main() {  
   Y y;  
   pin_ptr<int> p = &y.i;  
}  
```  
  
 다음 샘플에서는 C3831 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3831b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc class Y  
{  
};  
  
__gc class X  
{  
   Y __pin * mbr_Y;   // C3831  
   Y * mbr_Y2;   // OK  
  
   Y __pin * mf_Y()  // C3831  
   {  
      Y __pin * pY = new Y();  
      return pY;  
   }  
  
   Y * mf_Y2()   // OK  
   {  
      Y * pY = new Y();  
      return pY;  
   }  
};  
```