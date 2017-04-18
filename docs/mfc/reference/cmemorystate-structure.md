---
title: "CMemoryState 구조 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMemoryState
dev_langs:
- C++
helpviewer_keywords:
- CMemoryState structure
- memory leaks, detecting
- detecting memory leaks
ms.assetid: 229d9de7-a6f3-4cc6-805b-5a9d9b1bfe1d
caps.latest.revision: 19
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
translationtype: Machine Translation
ms.sourcegitcommit: bb94e24657d16b2a3eda3a770c2b6ae734c6006f
ms.openlocfilehash: 5485a3cf8107dd9b245cb2d3fff6982f31279abe
ms.lasthandoff: 04/12/2017

---
# <a name="cmemorystate-structure"></a>CMemoryState 구조
프로그램에서 메모리 누수 문제를 감지 하는 편리한 방법을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct CMemoryState  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMemoryState::CMemoryState](#cmemorystate)|메모리 검사점을 제어 하는 클래스와 유사한 구조를 생성 합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMemoryState::Checkpoint](#checkpoint)|현재 메모리 상태의 스냅숏으로 (검사점)을 가져옵니다.|  
|[CMemoryState::Difference](#difference)|형식의 두 개체 간의 차이 계산 `CMemoryState`합니다.|  
|[Cmemorystate:: Dumpallobjectssince](#dumpallobjectssince)|이전 검사점 이후 모든 현재 할당 된 개체의 요약을 덤프합니다.|  
|[CMemoryState::DumpStatistics](#dumpstatistics)|에 대 한 메모리 할당 통계 인쇄는 `CMemoryState` 개체입니다.|  
  
## <a name="remarks"></a>주의  
 `CMemoryState`구조체가 고 기본 클래스는 없습니다.  
  
 "메모리 누수" 개체에 대 한 메모리 힙에 할당 되는 더 이상 필요 하면 할당이 취소 되지 않는 경우 발생 합니다. 이러한 메모리 누수 결국 메모리 부족 오류가 발생할 수 있습니다. 여러 가지 방법으로 할당 하 고 프로그램에서 메모리 할당을 취소할 수 있습니다.  
  
-   사용 하는 `malloc` /  **무료** 런타임 라이브러리에서 함수 패밀리입니다.  
  
-   Windows API 메모리 관리 함수를 사용 하 여 **LocalAlloc**/ **LocalFree** 및 **GlobalAlloc**/ **작업**합니다.  
  
-   C + +를 사용 하 여 **새** 및 **삭제** 연산자입니다.  
  
 `CMemoryState` 진단만 메모리를 찾아내는 데 도움이 사용 하 여 메모리 할당 하는 경우에 발생 하는 누수는 **새** 연산자를 사용 하 여 할당 취소 됩니다 **삭제**합니다. 다른 두 그룹의 메모리 관리 함수는 비 c + + 프로그램 및를 사용 하 여 혼합 **새** 및 **삭제** 동일한 프로그램에서 권장 되지 않습니다. 추가 매크로 `DEBUG_NEW`, 대체 하기 위해 제공 됩니다는 **새** 연산자 파일 및 메모리 할당의 줄 번호 추적 해야 합니다. `DEBUG_NEW`일반적으로 사용 하려는 때마다 사용 되는 **새** 연산자입니다.  
  
 다른 진단와 마찬가지로 `CMemoryState` 진단이 프로그램의 디버그 버전에서 사용할 수만 있습니다. 디버그 버전 있어야는 **_DEBUG** 정의 되는 상수입니다.  
  
 사용할 수 있습니다 프로그램에 메모리 누수가 의심 되는 경우는 `Checkpoint`, **차이**, 및 `DumpStatistics` 프로그램 실행의 두 개의 서로 다른 지점에서 메모리 상태 (할당 된 개체) 간의 차이 검색 하는 함수입니다. 이 정보는 함수를 할당 한 모든 개체 정리 있는지 여부를 결정 하는 데 유용할 수 있습니다.  
  
 단순히 할당 및 할당 취소에 않으므로 이러한 불균형은 발생 한 위치를 알고 있으면 충분 한 정보 제공 하지 않는 경우 사용할 수 있습니다는 `DumpAllObjectsSince` 함수에 대 한 이전 호출 이후에 할당 된 모든 개체를 덤프를 `Checkpoint`합니다. 이 덤프의 할당, 소스 파일 및 줄 개체가 할당 된 순서를 보여 줍니다. (사용 중인 경우 `DEBUG_NEW` 할당에 대 한), 개체, 해당 주소 및 해당 크기의 파생 하 고 있습니다. `DumpAllObjectsSince`각 개체의 호출 `Dump` 함수를 현재 상태에 대 한 정보를 제공 합니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 `CMemoryState` 기타 진단 참조 및 [MFC 응용 프로그램 디버깅](/visualstudio/debugger/mfc-debugging-techniques)합니다.  
  
> [!NOTE]
>  형식 개체의 선언을 `CMemoryState` 멤버 함수에 대 한 호출을 묶은 해야 및 `#if defined(_DEBUG)/#endif` 지시문입니다. 그러면 메모리 진단 프로그램의 빌드를 디버깅에 포함 되도록 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CMemoryState`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
  
##  <a name="checkpoint"></a>CMemoryState::Checkpoint  
 스냅숏을 메모리 요약 하 고이 저장 `CMemoryState` 개체입니다.  
  
```  
void Checkpoint();
```  
  
### <a name="remarks"></a>주의  
 `CMemoryState` 멤버 함수 [차이](#difference) 및 [DumpAllObjectsSince](#dumpallobjectssince) 이 스냅숏 데이터를 사용 합니다.  
  
### <a name="example"></a>예제  
  예를 참조는 [CMemoryState](#cmemorystate) 생성자입니다.  
  
##  <a name="cmemorystate"></a>CMemoryState::CMemoryState  
 빈 생성 `CMemoryState` 은 입력 해야 하는 개체는 [검사점](#checkpoint) 또는 [차이](#difference) 멤버 함수입니다.  
  
```  
CMemoryState();
```  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities # 18](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]  
  
##  <a name="difference"></a>CMemoryState::Difference  
 두 `CMemoryState` 차이이를 저장 한 다음 개체를 `CMemoryState` 개체입니다.  
  
```  
BOOL Difference(
    const CMemoryState& oldState,   
    const CMemoryState& newState);
```  
  
### <a name="parameters"></a>매개 변수  
 *oldState*  
 에 정의 된 대로 초기 메모리 상태는 `CMemoryState` 검사점입니다.  
  
 *newState*  
 에 정의 된 대로 새로운 메모리 상태는 `CMemoryState` 검사점입니다.  
  
### <a name="return-value"></a>반환 값  
 두 메모리 상태가 서로 다른 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 [검사점](#checkpoint) 두 메모리 상태 매개 변수 마다 호출 합니다.  
  
### <a name="example"></a>예제  
  예를 참조는 [CMemoryState](#cmemorystate) 생성자입니다.  
  
##  <a name="dumpallobjectssince"></a>Cmemorystate:: Dumpallobjectssince  
 호출 된 `Dump` 클래스에서 파생 된 유형의 모든 개체에 대 한 함수 `CObject` 는 할당 된 (되며 여전히 할당) 마지막 이후 [검사점](#checkpoint) 이 대 한 호출 `CMemoryState` 개체입니다.  
  
```  
void DumpAllObjectsSince() const;

 
```  
  
### <a name="remarks"></a>주의  
 호출 `DumpAllObjectsSince` 초기화 되지 않은와 `CMemoryState` 모든 개체의 현재 메모리에에서 개체를 덤프 합니다.  
  
### <a name="example"></a>예제  
  예를 참조는 [CMemoryState](#cmemorystate) 생성자입니다.  
  
##  <a name="dumpstatistics"></a>CMemoryState::DumpStatistics  
 간결한 메모리 통계 보고서를 인쇄 하는 `CMemoryState` 로 채워진 개체는 [차이](#difference) 멤버 함수입니다.  
  
```  
void DumpStatistics() const;

 
```  
  
### <a name="remarks"></a>주의  
 에 인쇄 하는 보고서는 [afxDump](diagnostic-services.md#afxdump) 장치에서 다음을 보여 줍니다.  
  
 예제 보고서의 수 (또는 양)에 정보를 제공합니다.  
  
-   사용 가능한 블록  
  
-   일반 블록  
  
-   CRT 블록  
  
-   무시 블록  
  
-   클라이언트 블록  
  
-   최대 메모리 (바이트)에 한 번에 프로그램에서 사용  
  
-   총 메모리 (바이트)의 프로그램에서 현재 사용  
  
 Free 블록은 면 해당 할당 취소가 연기 된 블록 수가 `afxMemDF` 로 설정 된 **delayFreeMemDF**합니다. 자세한 내용은 참조 [afxMemDF](diagnostic-services.md#afxmemdf), "MFC 매크로 및 전역 변수" 섹션에 있습니다. 참조 [디버그 힙의 블록의 형식](http://msdn.microsoft.com/en-us/db2e7f62-0679-4b39-a23f-26f2c2f407c5) 블록 형식의 이러한 이벤트에 대해 자세한 정보에 대 한 합니다.  
  
### <a name="example"></a>예제  
  다음 코드에 배치 해야 *projname*App.cpp 합니다. 다음 전역 변수를 정의 합니다.  
  
 [!code-cpp[NVC_MFC_Utilities # 40](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]  
  
 에 `InitInstance` 함수, 줄 추가:  
  
 [!code-cpp[NVC_MFC_Utilities # 41](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]  
  
 에 대 한 처리기를 추가 `ExitInstance` 작동 하 고 다음 코드를 사용 합니다.  
  
 [!code-cpp[NVC_MFC_Utilities # 42](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]  
  
 출력을 보려면 디버그 모드에서 이제 프로그램을 실행할 수 있습니다는 `DumpStatistics` 함수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)




