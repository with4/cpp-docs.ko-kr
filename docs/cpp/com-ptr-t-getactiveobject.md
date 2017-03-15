---
title: "_com_ptr_t::GetActiveObject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t.GetActiveObject"
  - "_com_ptr_t::GetActiveObject"
  - "GetActiveObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetActiveObject 메서드"
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# _com_ptr_t::GetActiveObject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 **CLSID** 또는 **ProgID**가 지정된 개체의 기존 인스턴스에 연결합니다.  
  
## 구문  
  
```  
  
      HRESULT GetActiveObject(  
   const CLSID& rclsid   
) throw( );  
HRESULT GetActiveObject(  
   LPCWSTR clsidString   
) throw( );  
HRESULT GetActiveObject(  
   LPCSTR clsidStringA   
) throw( );  
```  
  
#### 매개 변수  
 `rclsid`  
 개체의 **CLSID**입니다.  
  
 `clsidString`  
 **CLSID**\("**{**"로 시작\) 또는 **ProgID**를 보유하는 유니코드 문자열입니다.  
  
 `clsidStringA`  
 **CLSID**\("**{**"로 시작\) 또는 **ProgID**를 보유하고 있고 ANSI 코드 페이지를 사용하는 멀티바이트 문자열입니다.  
  
## 설명  
 이러한 멤버 함수는 `GetActiveObject`를 호출하여 OLE에 등록된 실행 개체에 대한 포인터와 이 스마트 포인터의 인터페이스 형식에 대한 쿼리를 검색합니다.  그러면 결과 포인터는 이 `_com_ptr_t` 개체 안에 캡슐화됩니다.  **릴리스**는 이전에 캡슐화된 포인터의 참조 횟수를 감소시키기 위해 호출됩니다.  이 루틴은 `HRESULT`를 반환하여 성공 또는 실패를 나타냅니다.  
  
-   **GetActiveObject\(** `rclsid` **\) CLSID**가 지정된 개체의 기존 인스턴스에 연결합니다.  
  
-   **GetActiveObject\(** `clsidString` **\) CLSID**\("**{**"로 시작\) 또는 **ProgID** 중 하나를 포함하는 유니코드 문자열이 지정된 개체의 기존 인스턴스에 연결합니다.  
  
-   **GetActiveObject\(** `clsidStringA` **\) CLSID**\("**{**"로 시작\) 또는 **ProgID** 중 하나를 포함하는 멀티바이트 문자열이 지정된 개체의 기존 인스턴스에 연결합니다.  문자열이 OEM 코드 페이지가 아닌 ANSI 코드 페이지에 있다고 가정하는 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)를 호출합니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_com\_ptr\_t 클래스](../cpp/com-ptr-t-class.md)