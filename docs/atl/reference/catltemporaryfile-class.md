---
title: "CAtlTemporaryFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAtlTemporaryFile"
  - "ATL.CAtlTemporaryFile"
  - "ATL::CAtlTemporaryFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlTemporaryFile class"
ms.assetid: 05f0f2a5-94f6-4594-8dae-b114292ff5f9
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CAtlTemporaryFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 만들기 및 임시 파일의 사용에 대 한 메서드를 제공합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CAtlTemporaryFile  
  
```  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CAtlTemporaryFile::CAtlTemporaryFile](../Topic/CAtlTemporaryFile::CAtlTemporaryFile.md)|생성자입니다.|  
|[CAtlTemporaryFile::~CAtlTemporaryFile](../Topic/CAtlTemporaryFile::~CAtlTemporaryFile.md)|소멸자|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CAtlTemporaryFile::Close](../Topic/CAtlTemporaryFile::Close.md)|임시 파일을 닫으려면이 메서드를 호출 하 고 하나 내용을 삭제 하거나 지정한 파일 이름으로 저장 합니다.|  
|[CAtlTemporaryFile::Create](../Topic/CAtlTemporaryFile::Create.md)|임시 파일을 만들려면이 메서드를 호출 합니다.|  
|[CAtlTemporaryFile::Flush](../Topic/CAtlTemporaryFile::Flush.md)|임시 파일에 쓸 파일 버퍼에 남아 있는 데이터를 사용 하도록이 메서드를 호출 합니다.|  
|[CAtlTemporaryFile::GetPosition](../Topic/CAtlTemporaryFile::GetPosition.md)|현재 파일 포인터 위치를 가져오려면이 메서드를 호출 합니다.|  
|[CAtlTemporaryFile::GetSize](../Topic/CAtlTemporaryFile::GetSize.md)|임시 파일의 바이트 크기를 가져오려면이 메서드를 호출 합니다.|  
|[CAtlTemporaryFile::HandsOff](../Topic/CAtlTemporaryFile::HandsOff.md)|파일의 연결을 해제 하려면이 메서드를 호출 하는 `CAtlTemporaryFile` 개체입니다.|  
|[CAtlTemporaryFile::HandsOn](../Topic/CAtlTemporaryFile::HandsOn.md)|기존 임시 파일을 열고 파일의 끝에 포인터를이 메서드를 호출 합니다.|  
|[CAtlTemporaryFile::LockRange](../Topic/CAtlTemporaryFile::LockRange.md)|영역에서 다른 프로세스에 액세스 하지 못하도록 파일을 잠그려면이 메서드를 호출 합니다.|  
|[CAtlTemporaryFile::Read](../Topic/CAtlTemporaryFile::Read.md)|파일 포인터가 가리키는 위치부터 임시 파일에서 데이터 읽기에이 메서드를 호출 합니다.|  
|[CAtlTemporaryFile::Seek](../Topic/CAtlTemporaryFile::Seek.md)|임시 파일의 파일 포인터를 이동 하려면이 메서드를 호출 합니다.|  
|[CAtlTemporaryFile::SetSize](../Topic/CAtlTemporaryFile::SetSize.md)|임시 파일의 크기를 설정 하려면이 메서드를 호출 합니다.|  
|[CAtlTemporaryFile::TempFileName](../Topic/CAtlTemporaryFile::TempFileName.md)|임시 파일의 이름을 반환 하려면이 메서드를 호출 합니다.|  
|[CAtlTemporaryFile::UnlockRange](../Topic/CAtlTemporaryFile::UnlockRange.md)|영역을 임시 파일 잠금을 해제 하려면이 메서드를 호출 합니다.|  
|[CAtlTemporaryFile::Write](../Topic/CAtlTemporaryFile::Write.md)|파일 포인터가 가리키는 위치를 임시 파일에 데이터를 기록 하려면이 메서드를 호출 합니다.|  
  
### Public 연산자  
  
|이름|설명|  
|--------|--------|  
|[CAtlTemporaryFile::operator HANDLE](../Topic/CAtlTemporaryFile::operator%20HANDLE.md)|임시 파일에 핸들을 반환합니다.|  
  
## 설명  
 `CAtlTemporaryFile`쉽게 만들어 임시 파일을 사용할 수 있습니다.  파일 자동으로 명명 된, 열, 닫히고 삭제 합니다.  파일을 닫은 후 파일 내용을 필요한 경우 지정 된 이름의 새 파일로 저장할 수 있습니다.  
  
## 요구 사항  
 **헤더:** atlfile.h  
  
## 예제  
 예제를 보려면  [CAtlTemporaryFile::CAtlTemporaryFile](../Topic/CAtlTemporaryFile::CAtlTemporaryFile.md).  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)   
 [CAtlFile Class](../../atl/reference/catlfile-class.md)