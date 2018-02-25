---
title: "매크로 및 전역 함수에 대 한 OLE DB 소비자 템플릿 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.templates.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates, macros
- macros, OLE DB consumer template
ms.assetid: 8765eb7b-32dd-407c-bacf-8890ef959837
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 755762e8b77cee9603074fdc8050d227fbd2eeb1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="macros-and-global-functions-for-ole-db-consumer-templates"></a>OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수
OLE DB 소비자 템플릿은 다음 매크로 및 전역 함수 같습니다.  
  
### <a name="global-functions"></a>전역 함수  
  
|||  
|-|-|  
|[AtlTraceErrorRecords](../../data/oledb/atltraceerrorrecords.md)|오류가 반환 되 면 OLE DB 오류 레코드 덤프 장치 정보를 덤프 합니다.|  
  
### <a name="accessor-map-macros"></a>접근자 맵 매크로  
  
|||  
|-|-|  
|[BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)|접근자 항목의 시작을 표시 합니다.|  
|[BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)|접근자 맵 항목의 시작을 표시합니다.|  
|[END_ACCESSOR](../../data/oledb/end-accessor.md)|접근자 항목의 끝을 표시합니다.|  
|[END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)|접근자 맵 항목의 끝을 표시 합니다.|  
  
### <a name="column-map-macros"></a>열 맵 매크로  
  
|||  
|-|-|  
|[BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)|사용자 레코드 클래스에 있는 열 지도 항목의 시작을 표시 합니다.|  
|[BLOB_ENTRY](../../data/oledb/blob-entry.md)|이진 대형 개체 (BLOB)에 바인딩하는 데 사용 합니다.|  
|[BLOB_ENTRY_LENGTH](../../data/oledb/blob-entry-length.md)|BLOB 데이터 열의 길이 보고합니다.|  
|[BLOB_ENTRY_LENGTH_STATUS](../../data/oledb/blob-entry-length-status.md)|길이 및 BLOB 데이터 열의 상태를 보고합니다.|  
|[BLOB_ENTRY_STATUS](../../data/oledb/blob-entry-status.md)|BLOB 데이터 열의 상태를 보고합니다.|  
|[BLOB_NAME](../../data/oledb/blob-name.md)|열 이름으로 이진 대형 개체를 바인딩하는 데 사용 합니다.|  
|[BLOB_NAME_LENGTH](../../data/oledb/blob-name-length.md)|BLOB 데이터 열의 길이 보고합니다.|  
|[BLOB_NAME_LENGTH_STATUS](../../data/oledb/blob-name-length-status.md)|길이 및 BLOB 데이터 열의 상태를 보고합니다.|  
|[BLOB_NAME_STATUS](../../data/oledb/blob-name-status.md)|BLOB 데이터 열의 상태를 보고합니다.|  
|[BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md)|행 집합에서 책갈피 항목을 나타냅니다. 책갈피 항목은 열 항목의 특별 한 종류입니다.|  
|[COLUMN_ENTRY](../../data/oledb/column-entry.md)|데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다.|  
|[COLUMN_ENTRY_EX](../../data/oledb/column-entry-ex.md)|데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 지원 `type`, *길이*, *정밀도*, `scale`, 및 *상태* 매개 변수입니다.|  
|[COLUMN_ENTRY_LENGTH](../../data/oledb/column-entry-length.md)|데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 지원 된 *길이* 변수입니다.|  
|[COLUMN_ENTRY_LENGTH_STATUS](../../data/oledb/column-entry-length-status.md)|데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 지원 *상태* 및 *길이* 매개 변수입니다.|  
|[COLUMN_ENTRY_PS](../../data/oledb/column-entry-ps.md)|데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 지원 *정밀도* 및 `scale` 매개 변수입니다.|  
|[COLUMN_ENTRY_PS_LENGTH](../../data/oledb/column-entry-ps-length.md)|데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 지원 된 *길이* 변수 *정밀도* 및 `scale` 매개 변수입니다.|  
|[COLUMN_ENTRY_PS_LENGTH_STATUS](../../data/oledb/column-entry-ps-length-status.md)|데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 지원 *상태* 및 *길이* 변수 *정밀도* 및 `scale` 매개 변수입니다.|  
|[COLUMN_ENTRY_PS_STATUS](../../data/oledb/column-entry-ps-status.md)|데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 지원 된 *상태* 변수 *정밀도* 및 `scale` 매개 변수입니다.|  
|[COLUMN_ENTRY_STATUS](../../data/oledb/column-entry-status.md)|데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 지원 된 *상태* 변수입니다.|  
|[COLUMN_ENTRY_TYPE](../../data/oledb/column-entry-type.md)|데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 지원 `type` 매개 변수입니다.|  
|[COLUMN_ENTRY_TYPE_SIZE](../../data/oledb/column-entry-type-size.md)|데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 지원 `type` 및 `size` 매개 변수입니다.|  
|[COLUMN_NAME](../../data/oledb/column-name.md)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다.|  
|[COLUMN_NAME_EX](../../data/oledb/column-name-ex.md)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 데이터 형식, 크기, 전체 자릿수, 소수 자릿수, 열 길이 및 열 상태의 사양을 지원합니다.|  
|[COLUMN_NAME_LENGTH](../../data/oledb/column-name-length.md)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 열 길이 지정을 지원합니다.|  
|[COLUMN_NAME_LENGTH_STATUS](../../data/oledb/column-name-length-status.md)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 열 길이 및 상태 지정을 지원합니다.|  
|[COLUMN_NAME_PS](../../data/oledb/column-name-ps.md)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 전체 자릿수 및 소수 자릿수의 사양을 지원합니다.|  
|[COLUMN_NAME_PS_LENGTH](../../data/oledb/column-name-ps-length.md)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 전체 자릿수, 소수 자릿수 및 열 길이 지정을 지원합니다.|  
|[COLUMN_NAME_PS_LENGTH_STATUS](../../data/oledb/column-name-ps-length-status.md)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 전체 자릿수, 소수 자릿수, 열 길이 및 상태 열 사양을 지원합니다.|  
|[COLUMN_NAME_PS_STATUS](../../data/oledb/column-name-ps-status.md)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 정밀도, 배율 및 열 상태의 사양을 지원합니다.|  
|[COLUMN_NAME_STATUS](../../data/oledb/column-name-status.md)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 열 상태의 사양을 지원합니다.|  
|[COLUMN_NAME_TYPE](../../data/oledb/column-name-type.md)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 데이터 형식 사양을 지원합니다.|  
|[COLUMN_NAME_TYPE_PS](../../data/oledb/column-name-type-ps.md)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 데이터 형식, 정밀도 및 배율을 지정할을 수 있습니다.|  
|[COLUMN_NAME_TYPE_SIZE](../../data/oledb/column-name-type-size.md)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 데이터 형식 및 크기의 사양을 지원합니다.|  
|[COLUMN_NAME_TYPE_STATUS](../../data/oledb/column-name-type-status.md)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 데이터 형식 및 열 상태의 사양을 지원합니다.|  
|[END_COLUMN_MAP](../../data/oledb/end-column-map.md)|열 맵 항목의 끝을 표시 합니다.|  
  
### <a name="command-macros"></a>명령 매크로  
  
|||  
|-|-|  
|[DEFINE_COMMAND](../../data/oledb/define-command.md)|사용 하는 경우 행 집합을 만드는 데 사용할 명령을 지정는 [CCommand](../../data/oledb/ccommand-class.md) 클래스입니다. 지정 된 응용 프로그램 유형 (ANSI 또는 유니코드)와 일치 하는 문자열 형식에만 허용 합니다. 사용 하는 것이 좋습니다. [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) 대신 `DEFINE_COMMAND`합니다.|  
|[DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md)|사용 하는 경우 행 집합을 만드는 데 사용할 명령을 지정는 [CCommand](../../data/oledb/ccommand-class.md) 클래스입니다. ANSI 및 유니코드 응용 프로그램을 지원합니다.|  
  
### <a name="parameter-map-macros"></a>매개 변수 맵 매크로  
  
|||  
|-|-|  
|[BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md)|사용자 레코드 클래스에 매개 변수가 맵 항목의 시작을 표시 합니다.|  
|[END_PARAM_MAP](../../data/oledb/end-param-map.md)|매개 변수가 맵 항목의 끝을 표시 합니다.|  
|[SET_PARAM_TYPE](../../data/oledb/set-param-type.md)|지정 `COLUMN_ENTRY` 를 수행 하는 매크로 `SET_PARAM_TYPE` 매크로 입력, 출력 또는 입력/출력으로 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)