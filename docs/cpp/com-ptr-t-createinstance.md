---
title: _com_ptr_t::CreateInstance | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_ptr_t::CreateInstance
dev_langs: C++
helpviewer_keywords: CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e4764cf615bf04e9f2b1c3c816becc5a58da35f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="comptrtcreateinstance"></a>_com_ptr_t::CreateInstance
**Microsoft 전용**  
  
 지정 된 개체의 새 인스턴스를 만듭니다는 **CLSID** 또는 **ProgID**합니다.  
  
## <a name="syntax"></a>구문  
  
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
  
#### <a name="parameters"></a>매개 변수  
 `rclsid`  
 **CLSID** 개체입니다.  
  
 `clsidString`  
 보유 하는 유니코드 문자열을 **CLSID** (부터는 "**{**") 또는 **ProgID**합니다.  
  
 `clsidStringA`  
 보유 하 고 있고 ANSI 코드 페이지를 사용 하는 멀티 바이트 문자열을 **CLSID** (부터는 "**{**") 또는 **ProgID**합니다.  
  
 `dwClsContext`  
 실행 코드를 실행하는 컨텍스트입니다.  
  
 `pOuter`  
 에 대 한 알 수 없는 외부 [집계](../atl/aggregation.md)합니다.  
  
## <a name="remarks"></a>설명  
 이러한 멤버 함수는 새로운 COM 개체를 만들고 이 스마트 포인터의 인터페이스 형식을 쿼리하기 위해 `CoCreateInstance`를 호출합니다. 그러면 결과 포인터는 이 `_com_ptr_t` 개체 안에 캡슐화됩니다. **릴리스** 이전에 캡슐화 된 포인터에 대 한 참조 횟수를 감소 시키기 위해 호출 됩니다. 이 루틴은 `HRESULT`를 반환하여 성공 또는 실패를 나타냅니다.  
  
-   **CreateInstance (** `rclsid` **,**`dwClsContext`**)** 지정 된 개체의 새 실행 중인 인스턴스를 만듭니다는 **CLSID**합니다.  
  
-   **CreateInstance (** `clsidString` **,**`dwClsContext`**)** 보유 하는 유니코드 문자열을 지정 된 개체의 새 실행 중인 인스턴스를 만듭니다는 **CLSID** (부터는 "**{**") 또는 **ProgID**합니다.  
  
-   **CreateInstance (** `clsidStringA` **,**`dwClsContext`**)** 보유 하 고 있고 멀티 바이트 문자열을 지정 된 개체의 새 실행 중인 인스턴스를 만듭니다는  **CLSID** (부터는 "**{**") 또는 **ProgID**합니다. 호출 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), 있다고 가정 하는 문자열이 OEM 코드 페이지가 아닌 ANSI 코드 페이지에 있습니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)