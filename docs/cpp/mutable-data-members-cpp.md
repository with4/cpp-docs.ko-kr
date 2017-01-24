---
title: "변경할 수 있는 데이터 멤버 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "mutable_cpp"
  - "mutable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mutable 키워드[C++]"
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 변경할 수 있는 데이터 멤버 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 키워드는 클래스의 비정적 데이터 멤버 중에서 const가 아닌 멤버에만 적용할 수 있습니다.  데이터 멤버가 `mutable`로 선언된 경우 **const** 멤버 함수에서 이 데이터 멤버에 값을 할당할 수 있습니다.  
  
## 구문  
  
```  
  
mutable member-variable-declaration;  
```  
  
## 설명  
 예를 들어 다음 코드는 `m_accessCount`가 `mutable`로 선언되었으므로 `GetFlag`가 const 멤버 함수이더라도 `GetFlag`를 통해 수정될 수 있기 때문에 오류 없이 컴파일됩니다.  
  
```  
// mutable.cpp  
class X  
{  
public:  
   bool GetFlag() const  
   {  
      m_accessCount++;  
      return m_flag;  
   }  
private:  
   bool m_flag;  
   mutable int m_accessCount;  
};  
  
int main()  
{  
}  
```  
  
## 참고 항목  
 [C\+\+ 키워드](../cpp/keywords-cpp.md)