---
title: DEFINE_COMMAND | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- DEFINE_COMMAND
dev_langs:
- C++
helpviewer_keywords:
- DEFINE_COMMAND macro
ms.assetid: 9d724968-e242-413c-9a13-e7175fccf9b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 51f975b0477d29fbb35880c796f52612456c32c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101473"
---
# <a name="definecommand"></a>DEFINE_COMMAND
사용 하는 경우 행 집합을 만드는 데 사용할 명령을 지정는 [CCommand](../../data/oledb/ccommand-class.md) 클래스입니다. 지정 된 응용 프로그램 유형 (ANSI 또는 유니코드)와 일치 하는 문자열 형식에만 허용 합니다.  
  
> [!NOTE]
>  사용 하는 것이 좋습니다. [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) 대신 `DEFINE_COMMAND`합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
DEFINE_COMMAND(x, szCommand)  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 *x*  
 [in] 사용자 레코드 (명령) 클래스의 이름입니다.  
  
 `szCommand`  
 [in] 사용 하는 경우 행 집합을 만들려면 사용할 수 있는 명령 문자열 [CCommand](../../data/oledb/ccommand-class.md)합니다.  
  
## <a name="remarks"></a>설명  
 지정 하는 명령 문자열에 명령 텍스트를 지정 하지 않으면 기본적으로 사용 됩니다는 [ccommand:: Open](../../data/oledb/ccommand-open.md) 메서드.  
  
 이 매크로 유니코드로 응용 프로그램을 작성 하는 경우 ANSI로 응용 프로그램을 작성 하는 경우 ANSI 문자열 또는 유니코드 문자열에 적용 합니다. 사용 하는 것이 좋습니다. [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) 대신 `DEFINE_COMMAND`전자 ANSI 또는 유니코드 응용 프로그램 종류에 관계 없이 유니코드 문자열을 수락 하기 때문에, 합니다.  
  
## <a name="example"></a>예제  
 참조 [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)