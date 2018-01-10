---
title: "CStrBufT 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStrBufT
- ATLSIMPSTR/ATL::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::SetLength
- ATLSIMPSTR/ATL::CStrBufT::AUTO_LENGTH
- ATLSIMPSTR/ATL::CStrBufT::SET_LENGTH
dev_langs: C++
helpviewer_keywords:
- strings [C++], custom memory management
- CStrBufT class
- shared classes, CStrBufT
ms.assetid: 6b50fa8f-87e8-4ed4-a229-157ce128710f
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8df7f6c1dbd9987a9f83ed5b33a4c97fd90fec7f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cstrbuft-class"></a>CStrBufT 클래스
이 클래스에 대 한 자동 리소스 정리 제공 `GetBuffer` 및 `ReleaseBuffer` 기존 호출 `CStringT` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```
template<typename TCharType>
class CStrBufT
```  
  
#### <a name="parameters"></a>매개 변수  
 *TCharType*  
 문자 형식을 `CStrBufT` 클래스입니다. 다음 중 하나일 수 있습니다.  
  
- `char`(문자열에 대 한 ANSI 문자)  
  
- `wchar_t`(문자열에 대 한 유니코드 문자)  
  
- **TCHAR** (ANSI 및 유니코드 문자열)에 대 한  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`PCXSTR`|상수 문자열에 대 한 포인터입니다.|  
|`PXSTR`|문자열에 대 한 포인터입니다.|  
|`StringType`|이 클래스 템플릿의 특수화에 의해 조작 될 버퍼가 문자열 형식입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CStrBufT::CStrBufT](#cstrbuft)|문자열 버퍼 개체에 대 한 생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CStrBufT::SetLength](#setlength)|연결 된 문자열 개체의 문자 버퍼 길이 설정합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CStrBufT::operator PCXSTR](#operator_pcxstr)|검색 한 **const** 연결 된 문자열 개체의 문자 버퍼에 대 한 포인터입니다.|  
|[CStrBufT::operator PXSTR](#operator_pxstr)|연결 된 문자열 개체의 문자 버퍼에 대 한 포인터를 검색합니다.|  
  
### <a name="public-constants"></a>공용 상수  
  
|이름|설명|  
|----------|-----------------|  
|[CStrBufT::AUTO_LENGTH](#auto_length)|릴리스에서 문자열의 새 길이 자동으로 결정 합니다.|  
|[CStrBufT::SET_LENGTH](#set_length)|GetBuffer 시 string 개체의 길이 설정 합니다.|  
  
## <a name="remarks"></a>설명  
 이 클래스에 대 한 호출을 대체 하기 위해 래퍼 클래스로 사용 됩니다 [GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) 및 [ReleaseBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer), 또는 [GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) 및 `ReleaseBuffer`합니다.  
  
 도우미 클래스로 주로 `CStrBufT` 방법에 대 한 걱정 없이 string 개체의 문자 버퍼를 사용 하는 개발자를 위한 편리한 방법을 제공 하거나 호출 하는 경우 `ReleaseBuffer`합니다. 이 없기 때문에 예외 또는 여러 기존 코드 경로가;의 경우 자연스럽 게 범위를 벗어나면으로 래퍼 개체 문자열 리소스를 확보 하기 소멸자 인해 발생 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsimpstr.h  
  
##  <a name="auto_length"></a>CStrBufT::AUTO_LENGTH  
 릴리스에서 문자열의 새 길이 자동으로 결정 합니다.  
  
```
static const DWORD AUTO_LENGTH = 0x01;
```  
  
### <a name="remarks"></a>설명  
 릴리스에서 문자열의 새 길이 자동으로 결정 합니다. Null로 끝나는 문자열 이어야 합니다.  
  
##  <a name="cstrbuft"></a>CStrBufT::CStrBufT  
 버퍼 개체를 만듭니다.  
  
```
CStrBufT(StringType& str, int nMinLength, DWORD dwFlags = AUTO_LENGTH) throw(...);
explicit CStrBufT(StringType& str) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `str`  
 버퍼와 연결 된 문자열 개체입니다. 일반적으로 개발자의 미리 정의 된 typedef 사용할지 **CStrBuf** ( **TCHAR** variant), **CStrBufA** ( `char` variant) 및 **CStrBufW**  ( `wchar_t` variant).  
  
 *nMinLength*  
 최소 길이 문자 버퍼입니다.  
  
 `dwFlags`  
 문자열 길이가 자동으로 결정 하는 경우를 결정 합니다. 다음 중 하나일 수 있습니다.  
  
- **AUTO_LENGTH** 문자열 길이 자동으로 결정 될 때 [CSimpleStringT::Release](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) 호출 됩니다. Null로 끝나는 문자열 이어야 합니다. 기본값입니다.  
  
- **SET_LENGTH** 문자열 길이 설정 하는 경우 [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) 호출 됩니다.  
  
### <a name="remarks"></a>설명  
 연결 된 문자열 개체에 대 한 문자열 버퍼를 만듭니다. 생성 되는 동안 [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) 또는 [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) 호출 됩니다.  
  
 복사 생성자가 참고 `private`합니다.  
  
##  <a name="operator_pcxstr"></a>CStrBufT::operator PCXSTR  
 C 스타일 문자열로 연결 된 문자열 개체에 저장 된 문자를 직접 액세스 합니다.  
  
```  
operator PCXSTR() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 문자열의 데이터에는 문자 포인터입니다.  
  
### <a name="remarks"></a>설명  
 String 개체의 문자 버퍼에 대 한 포인터를 반환 하려면이 함수를 호출 합니다. 이 포인터와 함께 문자열 개체의 내용은 변경할 수 없습니다.  
  
##  <a name="operator_pxstr"></a>CStrBufT::operator PXSTR  
 C 스타일 문자열로 연결 된 문자열 개체에 저장 된 문자를 직접 액세스 합니다.  
  
```
operator PXSTR() throw();
```  
  
### <a name="return-value"></a>반환 값  
 문자열의 데이터에는 문자 포인터입니다.  
  
### <a name="remarks"></a>설명  
 String 개체의 문자 버퍼에 대 한 포인터를 반환 하려면이 함수를 호출 합니다. 개발자는이 포인터와 함께 문자열 개체의 내용을 변경할 수 있습니다.  
  
##  <a name="pcxstr"></a>CStrBufT::PCXSTR  
 상수 문자열에 대 한 포인터입니다.  
  
```
typedef CSimpleStringT<TCharType>::PCXSTR PCXSTR;
```  
  
##  <a name="pxstr"></a>CStrBufT::PXSTR  
 문자열에 대 한 포인터입니다.  
  
```
typedef CSimpleStringT<TCharType>::PXSTR PXSTR;
```  
  
##  <a name="set_length"></a>CStrBufT::SET_LENGTH  
 에 있는 문자열 개체의 길이 설정 `GetBuffer` 시간입니다.  
  
```
static const DWORD SET_LENGTH = 0x02;
```  
  
### <a name="remarks"></a>설명  
 GetBuffer 시 string 개체의 길이 설정 합니다.  
  
 있는지 여부를 확인 [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) 및 [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) 문자열 버퍼 개체가 생성 될 때 호출 됩니다.  
  
##  <a name="setlength"></a>CStrBufT::SetLength  
 문자 버퍼의 길이 설정합니다.  
  
```
void SetLength(int nLength);
```  
  
### <a name="parameters"></a>매개 변수  
 `nLength`  
 String 개체의 문자 버퍼의 새 길이입니다.  
  
> [!NOTE]
>  생성자에 지정 된 최소 버퍼 길이 보다 작거나 같아야 합니다 `CStrBufT`합니다.  
  
### <a name="remarks"></a>설명  
 버퍼 개체를 나타내는 문자열의 길이 설정 하려면이 함수를 호출 합니다.  
  
##  <a name="stringtype"></a>CStrBufT::StringType  
 이 클래스 템플릿의 특수화에 의해 조작 될 버퍼가 문자열 형식입니다.  
  
```
typedef CSimpleStringT<TCharType> StringType;
```  
  
### <a name="remarks"></a>설명  
 **TCharType** 문자 형식이 클래스 템플릿을 특수화 하는 데 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)


