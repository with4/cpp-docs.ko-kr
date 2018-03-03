---
title: "속성 인덱스 선언 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- indexers
- default indexers
- defaults, indexers
- indexed properties, C++
ms.assetid: d898fdbc-2106-4b6a-8c5c-9f511d80fc2f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fbd1158dce82b2cc2ae7d15e7b66d6b9058d8c85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="property-index-declaration"></a>속성 인덱스 선언
인덱싱된 속성을 선언 하는 구문은 Visual c + + Managed Extensions for c + + 변경 되었습니다.  
  
 Managed Extensions 언어 지원 인덱싱된 속성의 두 가지 주요 단점은 클래스 수준 첨자; 제공할 수 즉, 모든 인덱싱된 속성은에 이름을 지정 하는 데 필요 하 고 따라서 방법이 있으면, 예를 들어에 직접 적용할 수 있는 관리 되는 아래 첨자 연산자를 제공 하는 `Vector` 또는 `Matrix` 클래스 개체입니다. 중요 한 단점이 less 잠시는 인덱싱된 속성에서 속성을 구분 하기 위해 시각적으로 어렵습니다 매개 변수 수가 것을 나타냅니다. 마지막으로 인덱싱된 속성에서 인덱싱되지 않은 속성 동일한 문제가 발생-접근자는 원자 단위로 간주 되지 않고 개별 메서드로 분리 하지 않습니다.  예:  
  
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
  
 여기서 볼 수 있듯이 구분 되며이 추가 매개 변수를 2를 지정 하거나 단일에 의해서만 차원 인덱스입니다. 새 구문에서 인덱서는 대괄호 ([,]) 수와 각 인덱스의 유형을 나타내는 및 인덱서의 이름 뒤에 의해 구별 됩니다.  
  
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
  
 새 구문에서 클래스의 개체에 직접 적용할 수 있는 클래스 수준 인덱서를 나타내기 위해는 `default` 키워드를 다시 사용 하 여 명시적 이름으로 대체 합니다. 예:  
  
```  
public ref class Matrix {  
private:  
   array<float, 2>^ mat;  
  
public:  
   // ok: class level indexer now  
   //  
   //     Matrix mat;  
   //     mat[ 0, 0 ] = 1;   
   //  
   // invokes the set accessor of the default indexer  
  
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
  
 새 구문에서 default 인덱싱된 속성을 지정한 경우 두 개의 다음 이름은 예약 되어: `get_Item` 및 `set_Item`합니다. 즉, 기본 인덱싱된 속성에 대해 생성 된 기본 이름은 다음과 같습니다.  
  
 참고 구문은 없습니다 단순 인덱스 단순 속성 구문을 유사 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 또는 인터페이스 내에서 멤버 선언(C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 