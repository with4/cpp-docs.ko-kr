---
title: 'Cdberrorinfo:: Getallerrorinfo | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CDBErrorInfo.GetAllErrorInfo
- CDBErrorInfo::GetAllErrorInfo
- ATL::CDBErrorInfo::GetAllErrorInfo
- GetAllErrorInfo
- CDBErrorInfo.GetAllErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- GetAllErrorInfo method
ms.assetid: 630049fa-d296-497a-bbf6-f5d3d71d271d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 590215ddc5c62e5c717aebe196bc33ce7d514e7a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cdberrorinfogetallerrorinfo"></a>CDBErrorInfo::GetAllErrorInfo
모든 유형의 오류 레코드에 포함 된 오류 정보를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```
HRESULT GetAllErrorInfo(ULONG ulRecordNum,  
   LCID lcid,  BSTR* pbstrDescription,  
   BSTR* pbstrSource = NULL,  
   GUID* pguid = NULL,  
   DWORD* pdwHelpContext = NULL,  
   BSTR* pbstrHelpFile = NULL) const throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 *ulRecordNum*  
 [in] 오류 정보를 반환할에 대 한 레코드의 0부터 시작 하는 수입니다.  
  
 `lcid`  
 [in] 반환할 오류 정보에 대 한 로캘 ID입니다.  
  
 `pbstrDescription`  
 [out] 오류 또는 로캘을 지원 하지 않는 경우 NULL에 대 한 텍스트 설명에 대 한 포인터입니다. 설명 부분을 참조하세요.  
  
 `pbstrSource`  
 [out] 오류를 발생 시킨 구성 요소의 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `pguid`  
 [out] 오류를 정의한 인터페이스의 GUID에 대 한 포인터입니다.  
  
 *pdwHelpContext*  
 [out] 오류에 대 한 도움말 컨텍스트 ID에 대 한 포인터입니다.  
  
 *pbstrHelpFile*  
 [out] 오류를 설명 하는 도움말 파일의 경로를 포함 하는 문자열에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하는 경우 `S_OK`입니다. 참조 [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) 에 *OLE DB Programmer's Reference* 다른 반환 값에 대 한 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="remarks"></a>설명  
 출력 값 `pbstrDescription` 호출 ierrorinfo:: Getdescription, 로캘을 지원 되지 않는 경우 또는 다음 조건이 모두 해당 하는 경우 값으로 NULL로 설정 하 여 내부적으로 가져옵니다.  
  
1.  값 `lcid` 미국 않습니다 영어 및  
  
2.  값 `lcid` 은 GetUserDefaultLCID에서 반환 된 값과 같지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [CDBErrorInfo 클래스](../../data/oledb/cdberrorinfo-class.md)