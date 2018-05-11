---
title: CGopherLocator 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CGopherLocator
- AFXINET/CGopherLocator
- AFXINET/CGopherLocator::CGopherLocator
- AFXINET/CGopherLocator::GetLocatorType
dev_langs:
- C++
helpviewer_keywords:
- CGopherLocator [MFC], CGopherLocator
- CGopherLocator [MFC], GetLocatorType
ms.assetid: 6fcc015f-5ae6-4959-b936-858634c71019
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 377708108f96a42d23dcf3aa5e8214d7bf9ffe5c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cgopherlocator-class"></a>CGopherLocator 클래스
Gopher 서버에서 gopher "로케이터"를 가져오고 로케이터 형식을 확인 하 고 로케이터를 사용할 수 있도록 [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)합니다.  
  
> [!NOTE]
>  클래스 `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` 및 해당 멤버 사용이 중단 된 Windows XP 플랫폼에서 작동 하지 않음 되었지만 이전 버전의 플랫폼에서 실행 되도록 계속 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CGopherLocator : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CGopherLocator::CGopherLocator](#cgopherlocator)|`CGopherLocator` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CGopherLocator::GetLocatorType](#getlocatortype)|Gopher 로케이터를 구문 분석 하 고 해당 특성을 결정 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CGopherLocator::operator LPCTSTR](#operator_lpctstr)|에 저장 된 문자에 직접 액세스는 `CGopherLocator` C 스타일 문자열로 개체입니다.|  
  
## <a name="remarks"></a>설명  
 해당 서버에서 정보를 검색할 수 전에 응용 프로그램 gopher 서버의 로케이터를 가져와야 합니다. 로케이터 있으면 게 불투명 토큰으로 로케이터를 처리 해야 합니다.  
  
 각 gopher 로케이터에 파일 또는 서버를 찾을 수의 형식을 결정 하는 특성이 있습니다. 참조 [GetLocatorType](#getlocatortype) gopher 로케이터 형식의 목록에 대 한 합니다.  
  
 에 대 한 호출 응용 프로그램 정상적으로 사용 하 여 로케이터 [CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) 를 특정 조각에 정보를 검색 합니다.  
  
 방법에 대 한 자세한 내용을 보려면 `CGopherLocator` 작동 하는 다른 MFC 인터넷 클래스 문서를 참조 하십시오. [인터넷 WinInet를 사용한 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CGopherLocator`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxinet.h  
  
##  <a name="cgopherlocator"></a>  CGopherLocator::CGopherLocator  
 이 멤버 함수를 만드는 호출 됩니다는 `CGopherLocator` 개체입니다.  
  
```  
CGopherLocator(const CGopherLocator& ref);
```  
  
### <a name="parameters"></a>매개 변수  
 `ref`  
 상수에 대 한 참조 `CGopherLocator` 개체입니다.  
  
### <a name="remarks"></a>설명  
 만들지 마십시오는 `CGopherLocator` 개체를 직접 합니다. 대신, 호출 [CGopherConnection::CreateLocator](../../mfc/reference/cgopherconnection-class.md#createlocator) 만들고에 대 한 포인터를 반환 하는 `CGopherLocator` 개체입니다.  
  
##  <a name="getlocatortype"></a>  CGopherLocator::GetLocatorType  
 이 로케이터 형식을 가져오는 함수를 호출 합니다.  
  
```  
BOOL GetLocatorType(DWORD& dwRef) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *dwRef*  
 에 대 한 참조는 `DWORD` 하는 locator 유형을 받습니다. 참조 **주의** 로케이터 형식의 테이블에 대 한 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다. Win32 함수 호출이 실패 한 경우 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) 오류의 원인을 확인 하기 위해 호출할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 가능한 종류는 다음과 같습니다.  
  
|값|의미|  
|-----------|-------------|  
|GOPHER_TYPE_TEXT_FILE|ASCII 텍스트 파일입니다.|  
|GOPHER_TYPE_DIRECTORY|추가 Gopher 항목의 디렉터리입니다.|  
|GOPHER_TYPE_CSO|CSO 전화 번호부 서버입니다.|  
|GOPHER_TYPE_ERROR|오류 상태를 나타냅니다.|  
|GOPHER_TYPE_MAC_BINHEX|BINHEX 형식의 Macintosh 파일입니다.|  
|GOPHER_TYPE_DOS_ARCHIVE|DOS 보관 파일입니다.|  
|GOPHER_TYPE_UNIX_UUENCODED|UUENCODED 파일입니다.|  
|GOPHER_TYPE_INDEX_SERVER|인덱스 서버입니다.|  
|GOPHER_TYPE_TELNET|텔넷 서버입니다.|  
|GOPHER_TYPE_BINARY|이진 파일입니다.|  
|GOPHER_TYPE_REDUNDANT|중복 된 서버입니다. 내에 포함 된 정보에는 주 서버의 중복 됩니다. 주 서버는 GOPHER_TYPE_REDUNDANT 형식을 가지 지 않은 마지막 디렉터리 항목입니다.|  
|GOPHER_TYPE_TN3270|TN3270 서버입니다.|  
|GOPHER_TYPE_GIF|GIF 그래픽 파일입니다.|  
|GOPHER_TYPE_IMAGE|이미지 파일입니다.|  
|GOPHER_TYPE_BITMAP|비트맵 파일입니다.|  
|GOPHER_TYPE_MOVIE|동영상 파일입니다.|  
|GOPHER_TYPE_SOUND|사운드 파일입니다.|  
|GOPHER_TYPE_HTML|HTML 문서입니다.|  
|GOPHER_TYPE_PDF|PDF 파일입니다.|  
|GOPHER_TYPE_CALENDAR|달력 파일입니다.|  
|GOPHER_TYPE_INLINE|인라인 파일입니다.|  
|GOPHER_TYPE_UNKNOWN|항목 형식을 알려져 있습니다.|  
|GOPHER_TYPE_ASK|Ask + 항목입니다.|  
|GOPHER_TYPE_GOPHER_PLUS|Gopher + 항목입니다.|  
  
##  <a name="operator_lpctstr"></a>  CGopherLocator::operator LPCTSTR  
 이 유용한 캐스팅 연산자를 null로 끝나는 C 문자열에 포함 된에 액세스할 수 있는 효율적인 방법 제공는 `CGopherLocator` 개체입니다.  
  
```  
operator LPCTSTR () const;  
```  
  
### <a name="return-value"></a>반환 값  
 문자열의 데이터에는 문자 포인터입니다.  
  
### <a name="remarks"></a>설명  
 문자가 복사 됩니다. 포인터에만 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CGopherFileFind 클래스](../../mfc/reference/cgopherfilefind-class.md)
