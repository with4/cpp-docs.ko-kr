---
title: "OLE DB 공급자에 문자열 저장 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "사용자 레코드, 편집"
ms.assetid: 36cb9635-067c-4cad-8f85-962f28026f6a
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# OLE DB 공급자에 문자열 저장
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL OLE DB 마법사는 MyProviderRS.h에 `CWindowsFile`이라는 기본 사용자 레코드를 만듭니다.  두 문자열을 처리하려면 `CWindowsFile`을 수정하거나 다음 코드에서와 같이 사용자 고유의 레코드를 추가합니다.  
  
```  
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
  
 데이터 멤버 `szCommand`와 `szText`는 두 문자열을 나타내고, 필요한 경우 `szCommand2`와 `szText2`를 추가 열에 제공합니다.  `dwBookmark` 데이터 멤버는 단순한 읽기 전용 공급자에는 필요하지 않지만 나중에 `IRowsetLocate` 인터페이스를 추가하는 데 사용됩니다. [단순한 읽기 전용 공급자의 기능 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md)을 참조하십시오.  `==` 연산자는 인스턴스를 비교합니다. 이 연산자를 구현하는 것은 선택 사항입니다.  
  
 이 작업을 마치면 공급자를 컴파일하고 실행할 수 있습니다.  공급자를 테스트하려면 일치하는 기능이 있는 소비자가 있어야 합니다.  [단순 소비자 구현](../../data/oledb/implementing-a-simple-consumer.md)에서 테스트 소비자를 만드는 방법을 볼 수 있습니다.  공급자와 함께 테스트 소비자를 실행합니다.  **Test Consumer** 대화 상자의 **Run** 단추를 클릭하여 테스트 소비자가 공급자에서 적절한 문자열을 검색하는지 확인합니다.  
  
 공급자를 성공적으로 테스트했으면 추가 인터페이스를 구현하여 기능을 향상시킬 수 있습니다.  [단순한 읽기 전용 공급자의 기능 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md)에서 예제를 참조하십시오.  
  
## 참고 항목  
 [단순한 읽기 전용 공급자 구현](../../data/oledb/implementing-the-simple-read-only-provider.md)