---
title: "CGopherFile 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ce90eb2baf4ce8f6ba0136a9efd503086b686aa6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cgopherfile-class"></a>CGopherFile 클래스
Gopher 서버에서 파일을 찾고 읽는 기능을 제공합니다.  
  
> [!NOTE]
>  클래스 `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` 및 해당 멤버 사용이 중단 된 Windows XP 플랫폼에서 작동 하지 않음 되었지만 이전 버전의 플랫폼에서 실행 되도록 계속 됩니다.  
  
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
 Gopher 서비스에서는 사용자가이 서비스는 주로 인터페이스로 메뉴 기반 정보를 찾기 위한 작동 하기 때문에 gopher 파일에 데이터를 쓸 수 있습니다. `CGopherFile` 멤버 함수 **쓰기**, `WriteString`, 및 `Flush` 에 대 한 구현 되지 않은 `CGopherFile`합니다. 이러한 함수를 호출는 `CGopherFile` 개체를 반환 된 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)합니다.  
  
 방법에 대 한 자세한 내용을 보려면 `CGopherFile` 작동 하는 다른 MFC 인터넷 클래스 문서를 참조 하십시오. [인터넷 WinInet를 사용한 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CGopherFile`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxinet.h  
  
##  <a name="cgopherfile"></a>CGopherFile::CGopherFile  
 이 멤버 함수를 생성 하 라고 하는 `CGopherFile` 개체입니다.  
  
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
 `hFile`  
 에 대 한 핸들은 `HINTERNET` 파일입니다.  
  
 `refLocator`  
 에 대 한 참조는 [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) 개체입니다.  
  
 `pConnection`  
 에 대 한 포인터는 [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) 개체입니다.  
  
 `hSession`  
 현재 인터넷 세션에 대 한 핸들입니다.  
  
 `pstrLocator`  
 Gopher 서버를 찾는 데 사용 하는 문자열에 대 한 포인터입니다. 참조 [Gopher 세션](cgopherlocator-class.md) gopher 로케이터에 대 한 자세한 내용은 합니다.  
  
 *dwLocLen*  
 바이트 수를 포함 하는 DWORD `pstrLocator`합니다.  
  
 `dwContext`  
 열리는 파일의 컨텍스트 식별자에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 필요한는 `CGopherFile` gopher 인터넷 세션 중 파일에서 읽을 개체입니다.  
  
 만들지 마십시오는 `CGopherFile` 개체를 직접 합니다. 대신, 호출 [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) gopher 서버에서 파일을 엽니다.  
  
## <a name="see-also"></a>참고 항목  
 [CInternetFile 클래스](../../mfc/reference/cinternetfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CInternetFile 클래스](../../mfc/reference/cinternetfile-class.md)   
 [CGopherLocator 클래스](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFileFind 클래스](../../mfc/reference/cgopherfilefind-class.md)   
 [CGopherConnection 클래스](../../mfc/reference/cgopherconnection-class.md)
