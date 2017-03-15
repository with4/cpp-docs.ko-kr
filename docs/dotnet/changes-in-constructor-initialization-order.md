---
title: "생성자 초기화 순서 변경 사항 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "생성자, C++"
ms.assetid: 8892c38d-6bf7-4cf7-ac8f-15e052135a79
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 생성자 초기화 순서 변경 사항
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 클래스 생성자의 초기화 순서가 Managed Extensions for C\+\+와 다르게 변경되었습니다.  
  
## 생성자 초기화 순서 비교  
 Managed Extensions for C\+\+에서는 생성자 초기화가 다음과 같은 순서로 수행되었습니다.  
  
1.  기본 클래스 생성자가 있는 경우 이 생성자가 호출됩니다.  
  
2.  클래스의 초기화 목록이 확인됩니다.  
  
3.  클래스 생성자의 코드 본문이 실행됩니다.  
  
 이 실행 순서는 네이티브 C\+\+ 프로그래밍과 같은 규칙을 따릅니다.  새로운 Visual C\+\+ 언어에서는 CLR 클래스의 경우 다음과 같은 실행 순서가 적용됩니다.  
  
1.  클래스의 초기화 목록이 확인됩니다.  
  
2.  기본 클래스 생성자가 있는 경우 이 생성자가 호출됩니다.  
  
3.  클래스 생성자의 코드 본문이 실행됩니다.  
  
 이러한 변경 내용은 CLR 클래스에만 적용되며 [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]의 네이티브 클래스는 이전 규칙을 계속 따릅니다.  두 경우 모두 특정 클래스의 전체 계층 구조 체인을 거슬러 올라가면서 이러한 규칙이 적용됩니다.  
  
 Managed Extensions for C\+\+를 사용하는 다음 코드 예제를 살펴 봅니다.  
  
```  
__gc class A  
{  
public:  
   A() : _n(1)  
   {  
   }  
  
protected:  
   int _n;  
};  
  
__gc class B : public A  
{  
public:  
   B() : _m(_n)  
   {  
   }  
private:  
   int _m;  
};  
```  
  
 위에서 설명한 생성자 초기화 순서에 따르면 `B` 클래스의 새 인스턴스를 만들 때 다음과 같은 실행 순서를 확인할 수 있습니다.  
  
1.  기본 클래스 `A`의 생성자가 호출됩니다.  `_n` 멤버가 `1`로 초기화됩니다.  
  
2.  `B` 클래스의 초기화 목록이 확인됩니다.  `_m` 멤버가 `1`로 초기화됩니다.  
  
3.  `B` 클래스의 코드 본문이 실행됩니다.  
  
 이제 동일한 코드를 새로운 Visual C\+\+ 구문으로 표현하면 다음과 같습니다.  
  
```  
ref class A  
{  
public:  
   A() : _n(1)  
   {  
   }  
  
protected:  
   int _n;  
};  
  
ref class B : A  
{  
public:  
   B() : _m(_n)  
   {  
   }  
private:  
   int _m;  
};  
```  
  
 새 구문에서 `B` 클래스의 새 인스턴스를 만들면 다음과 같은 실행 순서가 적용됩니다.  
  
1.  `B` 클래스의 초기화 목록이 확인됩니다.  `_m` 멤버가 `0`으로 초기화됩니다. `0`은 `_m` 클래스 멤버의 초기화되지 않은 값입니다.  
  
2.  기본 클래스 `A`의 생성자가 호출됩니다.  `_n` 멤버가 `1`로 초기화됩니다.  
  
3.  `B` 클래스의 코드 본문이 실행됩니다.  
  
 두 코드 예제의 구문은 비슷하지만 실행 결과는 서로 다릅니다.  `B` 클래스의 생성자는 기본 클래스 `A`의 값에 따라 해당 멤버를 초기화합니다.  그러나 `A` 클래스의 생성자가 아직 호출되지 않았습니다.  특히 기본 클래스 생성자에서 메모리 또는 리소스를 할당해야 상속된 클래스가 작동하는 경우 이러한 종속성으로 인해 문제가 발생할 수 있습니다.  
  
## Managed Extensions for C\+\+에서 Visual C\+\+ 2005로 전환  
 기본 클래스에서는 상속된 클래스의 동작을 알 수 없으므로 많은 경우 클래스 생성자의 실행 순서가 변경되어도 프로그래머에게는 별다른 영향이 없습니다.  그러나 위 코드 예제에서 볼 수 있듯이 상속된 클래스의 초기화 목록이 기본 클래스 멤버의 값에 의존하는 경우 상속된 클래스의 생성자가 크게 영향을 받을 수 있습니다.  코드를 Managed Extensions for C\+\+에서 새 구문으로 전환하는 경우 이러한 생성 코드를 클래스 생성자의 본문으로 옮기는 것이 좋습니다. 이렇게 하면 코드를 항상 마지막에 실행할 수 있습니다.  
  
## 참고 항목  
 [관리되는 형식\(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)   
 [생성자](../cpp/constructors-cpp.md)   
 [생성자 이니셜라이저](../misc/constructor-initializers.md)