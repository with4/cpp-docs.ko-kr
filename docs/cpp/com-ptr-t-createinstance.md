---
title: "_com_ptr_t::CreateInstance | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::CreateInstance"
  - "_com_ptr_t.CreateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateInstance 메서드"
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_ptr_t::CreateInstance
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 **CLSID** 또는 **ProgID**가 지정된 개체의 새 인스턴스를 만듭니다.  
  
## 구문  
  
```  
  
      HRESULT CreateInstance(  
   const CLSID& rclsid,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
HRESULT CreateInstance(  
   LPCWSTR clsidString,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
HRESULT CreateInstance(  
   LPCSTR clsidStringA,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
```  
  
#### 매개 변수  
 `rclsid`  
 개체의 **CLSID**입니다.  
  
 `clsidString`  
 **CLSID**\("**{**"로 시작\) 또는 **ProgID**를 보유하는 유니코드 문자열입니다.  
  
 `clsidStringA`  
 **CLSID**\("**{**"로 시작\) 또는 **ProgID**를 보유하고 있고 ANSI 코드 페이지를 사용하는 멀티바이트 문자열입니다.  
  
 `dwClsContext`  
 실행 코드를 실행하는 컨텍스트입니다.  
  
 `pOuter`  
 [집합체](../atl/aggregation.md)에서 알 수 없는 외부 형식입니다.  
  
## 설명  
 이러한 멤버 함수는 새로운 COM 개체를 만들고 이 스마트 포인터의 인터페이스 형식을 쿼리하기 위해 `CoCreateInstance`를 호출합니다.  그러면 결과 포인터는 이 `_com_ptr_t` 개체 안에 캡슐화됩니다.  **릴리스**는 이전에 캡슐화된 포인터의 참조 횟수를 감소시키기 위해 호출됩니다.  이 루틴은 `HRESULT`를 반환하여 성공 또는 실패를 나타냅니다.  
  
-   **CreateInstance\(**  `rclsid` **,**  `dwClsContext`  **\) CLSID**가 지정된 개체의 새 실행 인스턴스를 만듭니다.  
  
-   **CreateInstance\(**  `clsidString` **,**  `dwClsContext`  **\)** 유니코드 문자열을 지정하는 개체의 새 실행 인스턴스 만들기는 **CLSID**\("**{**"로 시작\) 또는 **ProgID** 중 하나를 포함합니다.  
  
-   **CreateInstance\(**  `clsidStringA` **,**  `dwClsContext`  **\)** 멀티바이트 문자를 지정하는 개체의 새 실행 인스턴스 만들기는 **CLSID**\("**{**"로 시작\) 또는 **ProgID** 중 하나를 포함합니다.  문자열이 OEM 코드 페이지가 아닌 ANSI 코드 페이지에 있다고 가정하는 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)를 호출합니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_com\_ptr\_t 클래스](../cpp/com-ptr-t-class.md)