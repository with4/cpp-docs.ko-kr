---
title: _com_ptr_t::GetActiveObject | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::GetActiveObject
dev_langs:
- C++
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ccff761cb9b738de9e2f0debc470746d1482ab56
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940370"
---
# <a name="comptrtgetactiveobject"></a>_com_ptr_t::GetActiveObject
**Microsoft 전용**  
  
 지정 된 개체의 기존 인스턴스에 연결 된 `CLSID` 또는 `ProgID`합니다.  
  
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
 *rclsid*  
 `CLSID` 개체입니다.  
  
 *clsidString*  
 중 하나를 포함 하는 유니코드 문자열을 `CLSID` (시작 "**{**") 또는 `ProgID`합니다.  
  
 *clsidStringA*  
 멀티 바이트 문자열을 보유 하는 ANSI 코드 페이지를 사용 하는 `CLSID` (시작 "**{**") 또는 `ProgID`합니다.  
  
## <a name="remarks"></a>설명  
 이러한 멤버 함수는 `GetActiveObject`를 호출하여 OLE에 등록된 실행 개체에 대한 포인터와 이 스마트 포인터의 인터페이스 형식에 대한 쿼리를 검색합니다. 그러면 결과 포인터는 이 `_com_ptr_t` 개체 안에 캡슐화됩니다. `Release` 이전에 캡슐화 된 포인터에 대 한 참조 횟수를 감소 시키기 위해 호출 됩니다. 이 루틴은 성공 또는 실패를 나타내는 HRESULT를 반환 합니다.  
  
-   **GetActiveObject (**`rclsid`**)** 지정 된 개체의 기존 인스턴스에 연결 된 `CLSID`합니다.      
  
-   **GetActiveObject (**`clsidString`**)** 중 하나를 포함 하는 유니코드 문자열을 지정 된 개체의 기존 인스턴스에 연결을 `CLSID` (부터는 "**{**") 또는 `ProgID`.      
  
-   **GetActiveObject (**`clsidStringA`**)** 보유 하는 멀티 바이트 문자열을 지정 된 개체의 기존 인스턴스에 연결 된 `CLSID` (부터는 "**{**") 또는 `ProgID`.     호출 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), OEM 코드 페이지가 아닌 ANSI 코드 페이지에서 해당 문자열은 가정 합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)