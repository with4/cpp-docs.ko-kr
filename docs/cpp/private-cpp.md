---
title: "private (C++) | Microsoft Docs"
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
  - "private_cpp"
  - "private"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "private 키워드[C++]"
ms.assetid: 94e99983-46a5-4e21-800c-28f8a7c6a8ff
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# private (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
private:  
   [member-list]  
private base-class  
```  
  
## 설명  
 클래스 멤버 목록 앞에 오는 `private` 키워드는 멤버 함수와 클래스의 friend에서만 멤버에 액세스하도록 지정합니다.  이 설정은 다음 액세스 지정자 또는 클래스 끝까지 선언된 모든 멤버에 적용됩니다.  
  
 기본 클래스 이름 앞에 오는 `private` 키워드는 기본 클래스의 공용 및 보호된 멤버가 파생 클래스의 전용 멤버라고 지정합니다.  
  
 클래스에서 멤버의 기본 액세스는 전용입니다.  구조체나 공용 구조체에서 멤버의 기본 액세스는 공용입니다.  
  
 기본 클래스의 기본 액세스는 클래스에 대해 전용이고 구조체에 대해 공용입니다.  공용 구조체에 기본 클래스를 사용할 수 없습니다.  
  
 관련 내용은 [클래스 멤버에 대한 액세스 제어](../cpp/friend-cpp.md)의 [friend](../cpp/public-cpp.md), [public](../cpp/protected-cpp.md), [protected](../misc/controlling-access-to-class-members.md) 및 멤버 액세스 테이블을 참조하세요.  
  
## \/clr 관련  
 CLR 형식에서 C\+\+ 액세스 지정자 키워드\(**public**, `private` 및 `protected`\)는 어셈블리와 관련된 형식 및 메서드의 표시 유형에 영향을 줄 수 있습니다.  자세한 내용은 [형식 멤버 표시 유형](../misc/type-and-member-visibility.md)을 참조하세요.  
  
> [!NOTE]
>  [\/LN](../build/reference/ln-create-msil-module.md)으로 컴파일된 파일은 이 동작의 영향을 받지 않습니다.  이 경우 관리되는 클래스\(공용 또는 전용\)가 모두 표시됩니다.  
  
## END \/clr 관련  
  
## 예제  
  
```  
// keyword_private.cpp  
class BaseClass {  
public:  
   // privMem accessible from member function  
   int pubFunc() { return privMem; }  
private:  
   void privMem;  
};  
  
class DerivedClass : public BaseClass {  
public:  
   void usePrivate( int i )  
      { privMem = i; }   // C2248: privMem not accessible  
                         // from derived class  
};  
  
class DerivedClass2 : private BaseClass {  
public:  
   // pubFunc() accessible from derived class  
   int usePublic() { return pubFunc(); }  
};  
  
int main() {  
   BaseClass aBase;  
   DerivedClass aDerived;  
   DerivedClass2 aDerived2;  
   aBase.privMem = 1;     // C2248: privMem not accessible  
   aDerived.privMem = 1;  // C2248: privMem not accessible  
                          //    in derived class  
   aDerived2.pubFunc();   // C2247: pubFunc() is private in  
                          //    derived class  
}  
```  
  
## 참고 항목  
 [클래스 멤버에 대한 액세스 제어](../misc/controlling-access-to-class-members.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)