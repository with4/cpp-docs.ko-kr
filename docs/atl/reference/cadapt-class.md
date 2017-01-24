---
title: "CAdapt Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAdapt"
  - "ATL.CAdapt<T>"
  - "ATL::CAdapt"
  - "ATL::CAdapt<T>"
  - "CAdapt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "& 연산자, 주소 연산자"
  - "adapter objects"
  - "주소 연산자"
  - "CAdapt class"
ms.assetid: 0bb695a5-72fe-43d1-8f39-7e4da6e34765
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAdapt Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 템플릿은 개체 주소 이외의 주소를 반환하도록 연산자 주소를 다시 정의하는 클래스를 래핑하는 데 사용됩니다.  
  
## 구문  
  
```  
  
      template <  
   class T  
>  
class CAdapt  
```  
  
#### 매개 변수  
 `T`  
 조정된 형식입니다.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAdapt::CAdapt](../Topic/CAdapt::CAdapt.md)|생성자입니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CAdapt::operator const T&](../Topic/CAdapt::operator%20const%20T&.md)|`m_T`에 대한 `const` 참조를 반환합니다.|  
|[CAdapt::operator T&](../Topic/CAdapt::operator%20T&.md)|`m_T`에 대한 참조를 반환합니다.|  
|[CAdapt::operator \<](../Topic/CAdapt::operator%20%3C.md)|조정된 형식의 개체를 `m_T`와 비교합니다.|  
|[CAdapt::operator \=](../Topic/CAdapt::operator%20=.md)|조정된 형식의 개체를 `m_T`에 할당합니다.|  
|[CAdapt::operator \=\=](../Topic/CAdapt::operator%20==.md)|조정된 형식의 개체를 `m_T`와 비교합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAdapt::m\_T](../Topic/CAdapt::m_T.md)|조정되는 데이터입니다.|  
  
## 설명  
 `CAdapt`는 개체의 주소 이외의 주소를 반환하도록 연산자의 주소\(`operator &`\)를 다시 정의하는 클래스를 래핑하는 데 사용되는 간단한 템플릿입니다.  이러한 클래스의 예로 ATL의 `CComBSTR`, `CComPtr`, `CComQIPtr` 클래스 및 컴파일러 COM 지원 클래스인 `_com_ptr_t`가 있습니다.  이러한 모든 클래스가 데이터 멤버 중 하나의 주소를 반환하도록 연산자 주소를 다시 정의합니다\(`CComBSTR`의 경우 `BSTR` 및 기타 클래스의 경우 인터페이스 포인터\).  
  
 `CAdapt`의 주요 역할은 클래스 `T`에서 정의된 연산자의 주소를 숨기지만 조정된 클래스의 특성을 유지하는 것입니다.  `CAdapt`는 `T` 형식의 공용 멤버인 [m\_T](../Topic/CAdapt::m_T.md)를 유지하고, `CAdapt`의 특수화가 `T` 형식의 개체처럼 처리되도록 변환 연산자, 비교 연산자 및 복사 생성자를 정의하여 이 역할을 수행합니다.  
  
 어댑터 클래스 `CAdapt`는 일부 컨테이너 스타일 클래스가 연산자 주소를 사용하여 포함된 개체의 주소를 가져올 수 있기 때문에 유용합니다.  연산자의 주소를 다시 정의하면 일반적으로 컴파일 오류가 발생하고 "작동"해야 하는 클래스에서 조정되지 않은 형식이 사용되지 않아 이 요구 사항에 맞지 않게 됩니다.  `CAdapt`가 이러한 문제에 대한 해결 방법을 제공합니다.  
  
 일반적으로 컨테이너 스타일 클래스에 `CComBSTR`, `CComPtr`, `CComQIPtr` 또는 `_com_ptr_t` 개체를 저장하려는 경우 `CAdapt`를 사용합니다.  이는 C\+\+11 표준이 지원되기 전에 C\+\+ 표준 라이브러리 컨테이너에 대해 가장 일반적으로 필요했지만, 이제 C\+\+11 표준 라이브러리 컨테이너가 `operator&()`를 오버로드한 형식으로 자동으로 작동합니다.  표준 라이브러리가 개체의 실제 주소를 가져오기 위해 [std::addressof\(\)](../Topic/addressof.md)를 내부적으로 사용하여 이를 수행합니다.  
  
## 요구 사항  
 **헤더:** atlcomcli.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)