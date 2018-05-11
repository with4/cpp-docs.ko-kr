---
title: DEFINE_COMMAND_EX | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- DEFINE_COMMAND_EX
dev_langs:
- C++
helpviewer_keywords:
- DEFINE_COMMAND_EX macro
ms.assetid: d3e2ef20-1455-46d2-8499-8ab84bbb90a4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b2a77fa0d6655edeee88df3c7c45e1936a766b40
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="definecommandex"></a>DEFINE_COMMAND_EX
사용 하는 경우 행 집합을 만드는 데 사용할 명령을 지정는 [CCommand](../../data/oledb/ccommand-class.md) 클래스입니다. ANSI 및 유니코드 응용 프로그램을 지원합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
DEFINE_COMMAND_EX(x, wszCommand)  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 *x*  
 [in] 사용자 레코드 (명령) 클래스의 이름입니다.  
  
 `wszCommand`  
 [in] 사용 하는 경우 행 집합을 만들려면 사용할 수 있는 명령 문자열 [CCommand](../../data/oledb/ccommand-class.md)합니다.  
  
## <a name="remarks"></a>설명  
 지정 하는 명령 문자열에 명령 텍스트를 지정 하지 않으면 기본적으로 사용 됩니다는 [ccommand:: Open](../../data/oledb/ccommand-open.md) 메서드.  
  
 이 매크로 응용 프로그램 종류에 관계 없이 유니코드 문자열을 허용합니다. 이 매크로 선호 [DEFINE_COMMAND](../../data/oledb/define-command.md) 유니코드를 지원 하기 때문에 ANSI 응용 프로그램 및입니다.  
  
## <a name="example"></a>예제  
 참조 [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)