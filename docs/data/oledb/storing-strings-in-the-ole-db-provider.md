---
title: OLE DB 공급자에 문자열 저장 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- user records, editing
ms.assetid: 36cb9635-067c-4cad-8f85-962f28026f6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a5ba289e7e53ba1bcaca550ba84c2d871d215306
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="storing-strings-in-the-ole-db-provider"></a>OLE DB 공급자에 문자열 저장
MyProviderRS.h, ATL OLE DB 공급자 마법사 라는 기본 사용자 레코드를 만듭니다. `CWindowsFile`합니다. 수정 하거나 두 문자열을 처리 하려면 `CWindowsFile` 또는 다음 코드에 표시 된 대로 사용자 고유의 레코드를 추가 합니다.  
  
```cpp
////////////////////////////////////////////////////////////////////////  
class CAgentMan:   
   public WIN32_FIND_DATA  
   DWORD dwBookmark;              // Add this  
   TCHAR szCommand[256];          // Add this  
   TCHAR szText[256];             // Add this  
   TCHAR szCommand2[256];         // Add this  
   TCHAR szText2[256];            // Add this  
  
{  
public:  
BEGIN_PROVIDER_COLUMN_MAP()  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Command"), 1, 256, GUID_NULL, CAgentMan, szCommand)  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Text"), 2, 256, GUID_NULL, CAgentMan, szText)   
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Command2"), 3, 256, GUID_NULL, CAgentMan, szCommand2)  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Text2"),4, 256, GUID_NULL, CAgentMan, szText2)  
END_PROVIDER_COLUMN_MAP()  
   bool operator==(const CAgentMan& am) // This is optional   
   {  
      return (lstrcmpi(cFileName, wf.cFileName) == 0);  
   }  
};  
```  
  
 데이터 멤버 `szCommand` 및 `szText` 두 문자열을 나타낼 `szCommand2` 및 `szText2` 필요한 경우 추가 열을 제공 합니다. 데이터 멤버 `dwBookmark` 이 단순한 읽기 전용 공급자에는 필요 하지 않지만 나중에 추가 하는 데 사용 되는 `IRowsetLocate` 인터페이스; 참조 [단순한 읽기 전용 공급자의 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md)합니다. `==` 연산자 인스턴스를 비교 (구현이 연산자는 선택 사항).  
  
 이 도구를 실행 하는 경우 공급자를 컴파일 및 실행 준비가 됩니다. 공급자를 테스트 하려면이 기능을 일치 하는 소비자가 있어야 합니다. [단순 소비자 구현](../../data/oledb/implementing-a-simple-consumer.md) 에서 테스트 소비자를 만드는 방법을 보여 줍니다. 테스트 소비자는 공급자와 함께 실행 합니다. 클릭할 때 테스트 소비자의 공급자에서 적절 한 문자열 검색 있는지 확인 하십시오.는 **실행** 단추는 **테스트 소비자** 대화 상자.  
  
 공급자를 성공적으로 테스트 하는 경우에 추가 인터페이스를 구현 하 여 기능을 향상 하는 것이 좋습니다. 예제를 [단순한 읽기 전용 공급자 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [단순한 읽기 전용 공급자 구현](../../data/oledb/implementing-the-simple-read-only-provider.md)