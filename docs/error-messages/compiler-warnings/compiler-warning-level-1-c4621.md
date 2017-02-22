---
title: "컴파일러 경고 (수준 1) C4621 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4621"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4621"
ms.assetid: 40931bd9-cb89-497e-86f0-cec9f016c63c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 1) C4621
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' 형식에 대한 'operator \-\-' 후위 형식이 없으므로 전위 형식이 사용됩니다.  
  
 주어진 형식에 대해 정의된 후위 감소 연산자가 없으므로  컴파일러에서 오버로드된 전위 연산자를 사용했습니다.  
  
 이 경고가 발생하지 않도록 하려면 후위 `--` 연산자를 정의합니다.  두 인수 버전의 `--` 연산자를 다음과 같이 만드십시오.  
  
```  
// C4621.cpp  
// compile with: /W1  
class A  
{  
public:  
   A(int nData) : m_nData(nData)  
   {  
   }  
  
   A operator--()  
   {  
      m_nData -= 1;  
      return *this;  
   }  
  
   // A operator--(int)  
   // {  
   //    A tmp = *this;  
   //    m_nData -= 1;  
   //    return tmp;  
   // }  
  
private:  
   int m_nData;  
};  
  
int main()  
{  
   A a(10);  
   --a;  
   a--;   // C4621  
}  
```