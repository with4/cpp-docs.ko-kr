---
title: "속성 인덱스 선언 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "기본 인덱서"
  - "기본, 인덱서"
  - "인덱싱된 속성, C++"
  - "인덱서"
ms.assetid: d898fdbc-2106-4b6a-8c5c-9f511d80fc2f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 속성 인덱스 선언
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 인덱싱된 속성을 선언하는 구문이 Managed Extensions for C\+\+와 다르게 변경되었습니다.  
  
 인덱싱된 속성에 대한 Managed Extensions 언어 지원의 두 가지 주요 단점은 클래스 수준 첨자를 제공할 수 없으므로 모든 인덱싱된 속성에 이름을 지정해야 하며, 이로 인해 예를 들어 `Vector` 또는 `Matrix` 클래스 개체에 직접 적용할 수 있는 관리되는 첨자 연산자를 제공할 수 없다는 것입니다.  첫 번째보다 다소 중요성이 덜한 두 번째 단점은 속성과 인덱싱된 속성은 매개 변수 개수에만 차이가 있으므로 시각적으로 구분하기가 어렵다는 것입니다.  마지막으로, 인덱싱된 속성에는 인덱싱되지 않은 속성과 마찬가지로 접근자가 원자 단위로 취급되지 않지만 개별 메서드로 분리된다는 문제점이 있습니다.  예를 들면 다음과 같습니다.  
  
```  
public __gc class Vector;  
public __gc class Matrix {  
   float mat[,];  
  
public:   
   __property void set_Item( int r, int c, float value);  
   __property float get_Item( int r, int c );  
  
   __property void set_Row( int r, Vector* value );  
   __property Vector* get_Row( int r );  
};  
```  
  
 위와 같이 인덱서는 2차원 또는 1차원 인덱스를 지정하는 추가 매개 변수에 의해서만 구분됩니다.  새 구문에서는 인덱서 이름 뒤에 나오는 대괄호\(\[,\]\)에 의해 인덱서가 구분되며 이 대괄호에서는 인덱스의 수와 각 인덱스의 형식을 지정합니다.  
  
```  
public ref class Vector {};  
public ref class Matrix {  
private:  
   array<float, 2>^ mat;  
  
public:  
   property float Item [int,int] {  
      float get( int r, int c );  
      void set( int r, int c, float value );  
   }  
  
   property Vector^ Row [int] {  
      Vector^ get( int r );  
      void set( int r, Vector^ value );  
   }  
};  
```  
  
 새 구문에서 클래스 개체에 직접 적용할 수 있는 클래스 수준 인덱서를 지정하려면 `default` 키워드를 다시 사용하여 명시적 이름으로 대체합니다.  예를 들면 다음과 같습니다.  
  
```  
public ref class Matrix {  
private:  
   array<float, 2>^ mat;  
  
public:  
   // ok: class level indexer now  
   //  
   //     Matrix mat …  
   //     mat[ 0, 0 ] = 1;   
   //  
   // invokes the set accessor of the default indexer …  
  
   property float default [int,int] {  
      float get( int r, int c );  
      void set( int r, int c, float value );  
   }  
  
   property Vector^ Row [int] {  
      Vector^ get( int r );  
      void set( int r, Vector^ value );  
   }  
};  
```  
  
 새 구문에서 default 인덱싱된 속성이 지정되면 `get_Item` 및 `set_Item`과 같은 이름이 예약됩니다.  이는 default 인덱싱된 속성에 대해 내부적으로 이들 이름이 생성되기 때문입니다.  
  
 간단한 속성 구문에 대응시킬 수 있는 간단한 인덱스 구문은 없습니다.  
  
## 참고 항목  
 [클래스 또는 인터페이스 내에서 멤버 선언\(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [방법: 인덱싱된 속성 사용](../misc/how-to-use-indexed-properties.md)