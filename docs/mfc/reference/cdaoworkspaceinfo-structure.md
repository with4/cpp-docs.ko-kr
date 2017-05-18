---
title: "CDaoWorkspaceInfo 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoWorkspaceInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoWorkspaceInfo structure
- DAO (Data Access Objects), Workspaces collection
ms.assetid: a1f4b25e-f9c6-4196-b075-d1df99c54124
caps.latest.revision: 13
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 44c1ce365a1eecdb2a500998c082c6a9245dffb2
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoworkspaceinfo-structure"></a>CDaoWorkspaceInfo 구조체
`CDaoWorkspaceInfo` 구조에 데이터 액세스 개체 (DAO) 데이터베이스에 대해 정의 된 작업 영역에 대 한 정보가 들어 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct CDaoWorkspaceInfo  
{  
    CString m_strName;           // Primary  
    CString m_strUserName;       // Secondary  
    BOOL m_bIsolateODBCTrans;    // All  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 `m_strName`  
 작업 영역 개체의 고유 이름을 지정 합니다. 이 속성의 값을 직접 검색 하려면 쿼리 정의 개체의 호출 [GetName](../../mfc/reference/cdaoquerydef-class.md#getname) 멤버 함수입니다. 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 하십시오.  
  
 *m_strUserName*  
 Workspace 개체의 소유자를 나타내는 값입니다. 관련된 내용은 DAO 도움말의 "UserName 속성" 항목을 참조 합니다.  
  
 *m_bIsolateODBCTrans*  
 격리 된 같은 ODBC 데이터베이스와 관련 된 여러 트랜잭션을 지 여부를 나타내는 값입니다. 자세한 내용은 참조 [CDaoWorkspace::SetIsolateODBCTrans](../../mfc/reference/cdaoworkspace-class.md#setisolateodbctrans)합니다. 관련된 내용은 DAO 도움말에서 "IsolateODBCTrans 속성" 항목을 참조 합니다.  
  
## <a name="remarks"></a>주의  
 클래스의 개체를 영역은 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)합니다. 기본, 보조 및 위에서 모두에 대 한 참조에서의 정보를 반환 하는 방법을 나타내는 [GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) 클래스에서 멤버 함수 `CDaoWorkspace`합니다.  
  
 검색 한 정보는 [CDaoWorkspace::GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) 멤버 함수에 저장 되는 `CDaoWorkspaceInfo` 구조입니다. `CDaoWorkspaceInfo`또한 정의 `Dump` 디버그에서 멤버 함수를 작성 합니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 `CDaoWorkspaceInfo` 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoWorkspace 클래스](../../mfc/reference/cdaoworkspace-class.md)

