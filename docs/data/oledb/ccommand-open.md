---
title: 'Ccommand:: Open | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CCommand.Open
- ATL::CCommand::Open
- CCommand.Open
- CCommand::Open
dev_langs: C++
helpviewer_keywords: Open method
ms.assetid: 4c9b8f31-faf3-452d-9a29-3d3e5f54d6f8
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b6aa938d53cfdf11d5956a63d944dfb1bd6afea1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ccommandopen"></a>CCommand::Open
실행 하 고 필요에 따라 명령을 바인딩합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCWSTR wszCommand,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
HRESULT Open(  
   const CSession& session,  
   LPCSTR szCommand,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
HRESULT Open(  
   const CSession& session,  
   INT szCommand = NULL,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
HRESULT Open(  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `session`  
 [in] 세션에 명령을 실행 합니다.  
  
 `wszCommand`  
 [in] 명령이 실행을 유니코드 문자열로 전달 합니다. 수 **NULL** 사용 하는 경우 `CAccessor`, 전달 되는 값에서 명령을 검색할 수는 경우는 [DEFINE_COMMAND](../../data/oledb/define-command.md) 매크로입니다. 참조 [icommand:: Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) 에 *OLE DB Programmer's Reference* 대 한 자세한 내용은 합니다.  
  
 `szCommand`  
 [in] 와 동일 `wszCommand` 제외 하 고이 매개 변수에 ANSI 명령 문자열을 사용 합니다. 이 메서드의 네 번째 형식에 NULL 값을 걸릴 수 있습니다. 자세한 내용은이 항목의 뒷부분에 나오는 "주의"를 참조 하십시오.  
  
 *pPropSet*  
 [in] 배열에 대 한 포인터 [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 속성 및 값을 설정할 수를 포함 하는 구조체입니다. 참조 [속성 집합 및 속성 그룹](https://msdn.microsoft.com/en-us/library/ms713696.aspx) 에 *OLE DB Programmer's Reference* in the Windows SDK입니다.  
  
 `pRowsAffected`  
 [/ 출력] 명령에 의해 영향을 받는 행 수가 반환 되는 메모리에 대 한 포인터입니다. 경우  *\*pRowsAffected* 은 **NULL**, 없습니다 행 수가 반환 됩니다. 그렇지 않으면 **열려** 설정 *`pRowsAffected` 다음 조건에 따라:  
  
|조건|결과|  
|--------|----------|  
|**cParamSets** 요소의 `pParams` 1 보다 큰 경우|*`pRowsAffected`실행에 지정 된 매개 변수 집합의 모든 영향을 받는 행의 총 수를 나타냅니다.|  
|영향을 받는 행 수를 사용할 수 없는 경우|*`pRowsAffected`-1로 설정 됩니다.|  
|업데이트 되지 않습니다, 삭제 또는 행 삽입|*`pRowsAffected`정의 되지 않습니다.|  
  
 `guidCommand`  
 [in] 명령 텍스트를 구문 분석의 구문 및 사용 하도록 공급자에 대 한 일반 규칙을 지정 하는 GUID입니다. 참조 [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) 및 [icommandtext:: Setcommandtext](https://msdn.microsoft.com/en-us/library/ms709757.aspx) 에 *OLE DB Programmer's Reference* 대 한 자세한 내용은 합니다.  
  
 `bBind`  
 [in] 실행 되 고 후 명령을 자동으로 바인딩할 것인지 지정 합니다. 기본값은 **true**, 때문에 명령을 자동으로 바인딩할 수 있습니다. 설정 `bBind` 를 **false** 수동으로 바인딩할 수 있도록 명령 자동 바인딩 방지 합니다. (수동 바인딩은 OLAP 사용자에 게 특히 중요 합니다.)  
  
 `ulPropSets`  
 [in] 수가 [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 구조체에 전달 된 *pPropSet* 인수입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 에 처음 세 가지 **열려** 세션 걸릴 명령을 만들고 필요에 따라 매개 변수 바인딩 명령을 실행 합니다.  
  
 첫 번째 형태 **열려** 유니코드 명령 문자열을 사용 하며 기본값은 없습니다.  
  
 두 번째 형식의 **열려** ANSI 명령 문자열을 취하고 (기존 ANSI 응용 프로그램과 함께 이전 버전과 호환성을 위해 제공) 기본값이 없습니다.  
  
 세 번째 형태의 **열려** 명령 문자열 형식 때문에 NULL을 허용 `int` 이며 기본값은 NULL입니다. 호출을 위해 제공 됩니다 `Open(session, NULL);` 또는 `Open(session);` NULL 형식 이므로 `int`합니다. 이 버전을 차지 하며를 어설션하는 `int` 매개 변수가 NULL 이어야 합니다.  
  
 네 번째 양식을 사용 하 여 **열려** 명령을 이미 만든 시점과 단일 수행 하려는 [준비](../../data/oledb/ccommand-prepare.md) 및 실행이 여러 개 있습니다.  
  
> [!NOTE]
>  **열기** 호출 **Execute**를 호출 하 `GetNextResult`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CCommand 클래스](../../data/oledb/ccommand-class.md)