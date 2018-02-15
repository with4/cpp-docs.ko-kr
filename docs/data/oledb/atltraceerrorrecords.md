---
title: AtlTraceErrorRecords | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.AtlTraceErrorRecords
- ATL::AtlTraceErrorRecords
- AtlTraceErrorRecords
dev_langs:
- C++
helpviewer_keywords:
- AtlTraceErrorRecords function
ms.assetid: b83970b3-dc2a-445c-9142-f52218719905
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 95b743d9785d083b670be28e274b6f46acdea2ce
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="atltraceerrorrecords"></a>AtlTraceErrorRecords
오류가 반환 되 면 OLE DB 오류 레코드 덤프 장치 정보를 덤프 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      inline void AtlTraceErrorRecords(HRESULT hrErr = S_OK);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `hErr`  
 [in] `HRESULT` OLE DB 소비자 템플릿 멤버 함수에서 반환 합니다.  
  
## <a name="remarks"></a>설명  
 경우 `hErr` 않습니다 `S_OK`, `AtlTraceErrorRecords` 덤프 장치에 정보 OLE DB 오류 레코드 덤프 (의 **디버그** 출력 창 또는 파일의 탭). 오류 레코드 정보를 공급자에서 가져온 각 오류 레코드 항목에 대 한 행 번호, 소스, 설명, 도움말 파일, 컨텍스트 및 GUID를 포함 합니다. `AtlTraceErrorRecords` 디버그 빌드에서만에서이 정보를 덤프합니다. 릴리스 빌드 아웃 최적화 된 빈 스텁을입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역 함수에 대 한 OLE DB 소비자 템플릿](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [CDBErrorInfo 클래스](../../data/oledb/cdberrorinfo-class.md)