---
title: CDaoErrorInfo 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoErrorInfo structure [MFC]
- DAO (Data Access Objects), Errors collection
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c11ebaa7d315d09cea40b4ddc94d5afff498bf7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33366631"
---
# <a name="cdaoerrorinfo-structure"></a>CDaoErrorInfo 구조체
`CDaoErrorInfo` 구조 데이터 액세스 개체 (DAO)에 대해 정의 된 오류 개체에 대 한 정보를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct CDaoErrorInfo  
{  
    long m_lErrorCode;  
    CString m_strSource;  
    CString m_strDescription;  
    CString m_strHelpFile;  
    long m_lHelpContext;  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 *m_lErrorCode*  
 숫자 DAO 오류 코드입니다. 트랩 가능한 데이터 액세스의 "오류" DAO 도움말 항목을 참조 하십시오.  
  
 *m_strSource*  
 개체 또는 원래 오류를 생성 하는 응용 프로그램의 이름입니다. Source 속성을 원래; 오류를 생성 하는 개체를 표시 하는 문자열 식을 지정합니다 일반적으로 식은 개체의 클래스 이름입니다. 자세한 내용은 DAO 도움말의 "원본 Property" 항목을 참조 합니다.  
  
 *m_strDescription*  
 오류와 관련 된 설명 문자열입니다. 자세한 내용은 DAO 도움말의 "Description 속성" 항목을 참조 합니다.  
  
 *m_strHelpFile*  
 Microsoft Windows 도움말 파일에 정규화 된 경로입니다. 세부 정보를 DAO 도움말의 "HelpContext HelpFile 속성" 항목을 참조 합니다.  
  
 *m_lHelpContext*  
 Microsoft Windows 도움말 파일의 항목에 대 한 컨텍스트 ID입니다. 세부 정보를 DAO 도움말의 "HelpContext HelpFile 속성" 항목을 참조 합니다.  
  
## <a name="remarks"></a>설명  
 MFC는 클래스에서 DAO 오류 개체를 캡슐화 하지 않습니다. 대신,는 [CDaoException](../../mfc/reference/cdaoexception-class.md) 클래스에서 DAO에 포함 된 오류 컬렉션에 액세스 하기 위한 인터페이스를 제공 합니다. **DBEngine** 개체, 또한 모든 작업 영역을 포함 하는 개체입니다. MFC DAO 작업이 throw 하는 경우는 `CDaoException` catch, MFC 채웁니다 개체는 `CDaoErrorInfo` 구조체이 고 예외 개체에 저장 [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) 멤버입니다. (예외 개체를 호출 해야 직접 DAO 호출 하려는 경우 [GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) 멤버 함수에 맞게 직접 `m_pErrorInfo`.)  
  
 DAO 오류를 처리 하는 방법에 대 한 자세한 내용은 문서 참조 [예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md)합니다. 관련된 정보에 대 한 DAO 도움말의 "Error 개체" 항목을 참조 합니다.  
  
 검색 한 정보는 [CDaoException::GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) 멤버 함수에 저장 되는 `CDaoErrorInfo` 구조입니다. 검사는 [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) 에서 데이터 멤버는 `CDaoException` 예외 처리기 또는 호출에서 파악 하는 개체 `GetErrorInfo` 에서 `CDaoException` 있을 수 있는 오류를 확인 하기 위해 명시적으로 만든 개체 DAO 인터페이스를 직접 호출 하는 동안 발생 했습니다. `CDaoErrorInfo` 또한 정의 `Dump` 디버그에서 멤버 함수를 작성 합니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 `CDaoErrorInfo` 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoException 클래스](../../mfc/reference/cdaoexception-class.md)
