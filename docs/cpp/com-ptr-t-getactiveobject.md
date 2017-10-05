---
title: _com_ptr_t::GetActiveObject | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t.GetActiveObject
- _com_ptr_t::GetActiveObject
- GetActiveObject
dev_langs:
- C++
helpviewer_keywords:
- GetActiveObject method
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: a61e41c750fdf5865a475d92ba9e1def0aefd748
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="comptrtgetactiveobject"></a>_com_ptr_t::GetActiveObject
**Microsoft 전용**  
  
 지정 된 개체의 기존 인스턴스를 연결 된 **CLSID** 또는 **ProgID**합니다.  
  
## <a name="syntax"></a>구문  
  
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
  
#### <a name="parameters"></a>매개 변수  
 `rclsid`  
 **CLSID** 개체입니다.  
  
 `clsidString`  
 보유 하는 유니코드 문자열을 **CLSID** (부터는 "**{**") 또는 **ProgID**합니다.  
  
 `clsidStringA`  
 보유 하 고 있고 ANSI 코드 페이지를 사용 하는 멀티 바이트 문자열을 **CLSID** (부터는 "**{**") 또는 **ProgID**합니다.  
  
## <a name="remarks"></a>설명  
 이러한 멤버 함수는 `GetActiveObject`를 호출하여 OLE에 등록된 실행 개체에 대한 포인터와 이 스마트 포인터의 인터페이스 형식에 대한 쿼리를 검색합니다. 그러면 결과 포인터는 이 `_com_ptr_t` 개체 안에 캡슐화됩니다. **릴리스** 이전에 캡슐화 된 포인터에 대 한 참조 횟수를 감소 시키기 위해 호출 됩니다. 이 루틴은 `HRESULT`를 반환하여 성공 또는 실패를 나타냅니다.  
  
-   **GetActiveObject (**`rclsid`**)** 지정 된 개체의 기존 인스턴스를 연결 된 **CLSID**합니다.      
  
-   **GetActiveObject (**`clsidString`**)** 보유 하는 유니코드 문자열을 지정 된 개체의 기존 인스턴스를 연결 된 **CLSID** (부터는 "**{**") 또는 **ProgID**합니다.      
  
-   **GetActiveObject (**`clsidStringA`**)** 보유 하 고 있고 멀티 바이트 문자열을 지정 된 개체의 기존 인스턴스를 연결 된 **CLSID** (부터는 "**{**") 또는 **ProgID**합니다.     호출 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), 있다고 가정 하는 문자열이 OEM 코드 페이지가 아닌 ANSI 코드 페이지에 있습니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)
