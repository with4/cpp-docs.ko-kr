---
title: "오버로드된 연산자 | Microsoft Docs"
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
  - "연산자 오버로드, CLR 클래스"
  - "연산자[C++], 오버로드"
ms.assetid: 30391426-afe7-4497-bf22-e4816c1e48c8
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 오버로드된 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 연산자 오버로드가 Managed Extensions for C\+\+와 상당히 다르게 변경되었습니다.  
  
 예를 들어, 참조 형식의 선언에서 네이티브 `operator+` 구문을 사용하는 대신 연산자의 기본 내부 이름\(이 경우 `op_Addition`\)을 명시적으로 입력해야 합니다.  또한 이 이름을 통해 연산자를 명시적으로 호출해야 하므로 연산자 오버로드의 두 가지 주요 이점인 \(a\) 직관적인 구문 및 \(b\) 새 형식과 기존 형식을 함께 사용할 수 있는 기능을 활용할 수 없게 됩니다.  예를 들면 다음과 같습니다.  
  
```  
public __gc __sealed class Vector {  
public:  
   Vector( double x, double y, double z );  
  
   static bool    op_Equality( const Vector*, const Vector* );  
   static Vector* op_Division( const Vector*, double );  
   static Vector* op_Addition( const Vector*, const Vector* );  
   static Vector* op_Subtraction( const Vector*, const Vector* );  
};  
  
int main()  
{  
   Vector *pa = new Vector( 0.231, 2.4745, 0.023 );  
   Vector *pb = new Vector( 1.475, 4.8916, -1.23 );   
  
   Vector *pc1 = Vector::op_Addition( pa, pb );  
   Vector *pc2 = Vector::op_Subtraction( pa, pc1 );  
   Vector *pc3 = Vector::op_Division( pc1, pc2->x );  
  
   if ( Vector::op_Equality( pc1, pc2 ))  
      ;  
}  
```  
  
 새 구문에서는 정적 연산자를 선언하거나 사용할 때 모두 네이티브 C\+\+ 프로그래머가 일반적으로 바라는 작업 방식이 적용됩니다.  새 구문에서는 위의 `Vector` 클래스가 다음과 같이 변환됩니다.  
  
```  
public ref class Vector sealed {  
public:  
   Vector( double x, double y, double z );  
  
   static bool    operator ==( const Vector^, const Vector^ );  
   static Vector^ operator /( const Vector^, double );  
   static Vector^ operator +( const Vector^, const Vector^ );  
   static Vector^ operator -( const Vector^, const Vector^ );  
};  
  
int main()  
{  
   Vector^ pa = gcnew Vector( 0.231, 2.4745, 0.023 );  
   Vector^ pb = gcnew Vector( 1.475,4.8916,-1.23 );  
  
   Vector^ pc1 = pa + pb;  
   Vector^ pc2 = pa - pc1;  
   Vector^ pc3 = pc1 / pc2->x;  
  
   if ( pc1 == pc2 )  
      ;  
}  
```  
  
## 참고 항목  
 [클래스 또는 인터페이스 내에서 멤버 선언\(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)