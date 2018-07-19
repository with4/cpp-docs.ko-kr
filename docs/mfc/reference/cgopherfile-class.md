---
title: CGopherFile 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CGopherFile
- AFXINET/CGopherFile
- AFXINET/CGopherFile::CGopherFile
dev_langs:
- C++
helpviewer_keywords:
- CGopherFile [MFC], CGopherFile
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c6c4f87ffb1538e581320e9d6f36e8d4fbc6fc12
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335684"
---
# <a name="cgopherfile-class"></a>CGopherFile 클래스
Gopher 서버에서 파일을 찾고 읽는 기능을 제공합니다.  
  
> [!NOTE]
>  클래스 `CGopherConnection`, `CGopherFile`를 `CGopherFileFind`, `CGopherLocator` 및 해당 멤버는 사용 되지 않습니다 Windows XP 플랫폼에서 작동 하지 않습니다 하지만 계속 이전 플랫폼에서 작동 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CGopherFile : public CInternetFile  
```  
  
## <a name="members"></a>멤버  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CGopherFile::CGopherFile](#cgopherfile)|`CGopherFile` 개체를 생성합니다.|  
  
## <a name="remarks"></a>설명  
 Gopher 서비스에서는 사용자가이 서비스 정보를 찾기 위한 메뉴 기반 인터페이스로 서 주로 함수 gopher 파일로 데이터를 쓸 수 없습니다. 합니다 `CGopherFile` 멤버 함수 `Write`, `WriteString`, 및 `Flush` 에 대 한 구현 되지 않은 `CGopherFile`합니다. 이러한 함수를 호출을 `CGopherFile` 개체를 반환 된 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 하는 방법에 자세히 알아보려면 `CGopherFile` 문서를 참조 하는 다른 인터넷 MFC 클래스와 함께 작동 [WinInet을 사용 하 여 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CGopherFile`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxinet.h  
  
##  <a name="cgopherfile"></a>  CGopherFile::CGopherFile  
 이 멤버 함수를 생성 하 라고는 `CGopherFile` 개체입니다.  
  
```  
CGopherFile(
    HINTERNET hFile,  
    CGopherLocator& refLocator,  
    CGopherConnection* pConnection);

 
CGopherFile(
    HINTERNET hFile,  
    HINTERNET hSession,  
    LPCTSTR pstrLocator,  
    DWORD dwLocLen,  
    DWORD_PTR dwContext);
```  
  
### <a name="parameters"></a>매개 변수  
 *hFile*  
 HINTERNET 파일 핸들입니다.  
  
 *refLocator*  
 에 대 한 참조를 [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) 개체입니다.  
  
 *pConnection*  
 에 대 한 포인터를 [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) 개체입니다.  
  
 *hSession*  
 현재 인터넷 세션에 대 한 핸들입니다.  
  
 *pstrLocator*  
 Gopher 서버를 찾는 데 사용 하는 문자열에 대 한 포인터입니다. 참조 [Gopher 세션](cgopherlocator-class.md) gopher 로케이터에 대 한 자세한 내용은 합니다.  
  
 *dwLocLen*  
 바이트 수를 포함 하는 DWORD *pstrLocator*합니다.  
  
 *dwContext*  
 열려 있는 파일의 컨텍스트 식별자에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 필요한를 `CGopherFile` gopher 인터넷 세션 중 파일에서 읽을 개체입니다.  
  
 되지 만들기는 `CGopherFile` 직접 개체입니다. 대신, 호출 [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) gopher 서버에서 파일을 엽니다.  
  
## <a name="see-also"></a>참고 항목  
 [CInternetFile 클래스](../../mfc/reference/cinternetfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CInternetFile 클래스](../../mfc/reference/cinternetfile-class.md)   
 [CGopherLocator 클래스](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFileFind 클래스](../../mfc/reference/cgopherfilefind-class.md)   
 [CGopherConnection 클래스](../../mfc/reference/cgopherconnection-class.md)
