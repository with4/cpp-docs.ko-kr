---
title: "typename | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "typename"
  - "typename_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "typename 템플릿 지정자"
ms.assetid: 52e1d901-220d-4f0d-ab43-dae7e05fb491
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# typename
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

알 수 없는 식별자가 형식임을 컴파일러에 알립니다.  
  
## 구문  
  
```  
  
typename identifier;  
```  
  
## 설명  
 이 키워드는 템플릿 정의에서만 사용하십시오.  
  
 이름이 템플릿 인수에 종속된 정규화된 이름인 경우 이 키워드를 사용해야 하고, 정규화된 이름이 종속되어 있지 않은 경우에는 이 키워드가 선택 사항입니다.  자세한 내용은 [템플릿 및 이름 확인](../cpp/templates-and-name-resolution.md)을 참조하십시오.  
  
 **typename**은 템플릿 선언 또는 정의의 모든 위치에서 모든 형식에 의해 사용될 수 있지만  템플릿 기본 클래스의 템플릿 인수로 사용되지 않는 한 기본 클래스 목록에서는 허용되지 않습니다.  
  
```  
template <class T>  
class C1 : typename T::InnerType // Error - typename not allowed.  
{};  
template <class T>  
class C2 : A<typename T::InnerType>  // typename OK.  
{};  
```  
  
 템플릿 매개 변수 목록에서 **class** 대신 **typename** 키워드를 사용할 수도 있습니다.  예를 들어, 다음 문은 동일합니다.  
  
```  
template<class T1, class T2>...  
template<typename T1, typename T2>...  
```  
  
## 예제  
  
```  
// typename.cpp  
template<class T> class X  
{  
   typename T::Y m_y;   // treat Y as a type  
};  
  
int main()  
{  
}  
```  
  
## 참고 항목  
 [템플릿](../cpp/templates-cpp.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)