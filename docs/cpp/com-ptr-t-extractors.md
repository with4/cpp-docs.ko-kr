---
title: "_com_ptr_t 추출기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::operatorInterface&
- _com_ptr_t::operatorbool
- _com_ptr_t::operator->
- _com_ptr_t::operator*
dev_langs: C++
helpviewer_keywords:
- operator Interface& [C++]
- '* operator [C++], with specific objects'
- operator& [C++]
- operator* [C++]
- -> operator [C++], with specific objects
- '& operator [C++], with specific objects'
- operator Interface* [C++]
- operator * [C++]
- operator->
- operator bool
- extractors, _com_ptr_t class
- extractors [C++]
ms.assetid: 194b9e0e-123c-49ff-a187-0a7fcd68145a
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1c006c18b9e00e5c79ff686dfb31fa9ccf56fd4e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="comptrt-extractors"></a>_com_ptr_t Extractors
**Microsoft 전용**  
  
 캡슐화된 COM 인터페이스 포인터를 추출합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      operator Interface*( ) const throw( );   
operator Interface&( ) const;   
Interface& operator*( ) const;   
Interface* operator->( ) const;   
Interface** operator&( ) throw( );   
operator bool( ) const throw( );  
```  
  
## <a name="remarks"></a>설명  
  
-   **연산자 인터페이스\***  일 수 있는 캡슐화 된 인터페이스 포인터를 반환 **NULL**합니다.  
  
-   **연산자 인터페이스 &** 캡슐화 된 인터페이스 포인터에 대 한 참조를 반환 하 고에서 오류가 발생 하 여 포인터가 있으면 **NULL**합니다.  
  
-   **연산자\***  는 스마트 포인터 개체가 역참조 시 실제로 캡슐화 된 인터페이스인 것 처럼 작동 하도록 합니다.  
  
-   **operator->** 는 스마트 포인터 개체가 역참조 시 실제로 캡슐화 된 인터페이스인 것 처럼 작동 하도록 합니다.  
  
-   **연산자 &** 로 바꾸고, 모든 캡슐화 된 인터페이스 포인터를 해제 **NULL**, 캡슐화 된 포인터의 주소를 반환 합니다. 이렇게 하면 포함 된 함수를 주소로 전달 하도록 스마트 포인터는 **아웃** 인터페이스 포인터를 반환 하는 매개 변수입니다.  
  
-   **연산자 bool** 스마트 포인터 개체를 조건식에 사용할 수 있습니다. 이 연산자는 반환 **true** 포인터가 없으면 **NULL**합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)