---
title: "CMetaFileDC Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMetaFileDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMetaFileDC class"
  - "메타파일, 구현"
  - "Windows metafiles [C++]"
ms.assetid: ffce60fa-4181-4d46-9832-25e46fad4db4
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CMetaFileDC Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

원하는 이미지나 텍스트를 만들 수 재생할 수 있습니다 그래픽 장치 인터페이스 \(GDI\) 명령 시퀀스를 포함 하는 Windows 메타 파일을 구현 합니다.  
  
## 구문  
  
```  
class CMetaFileDC : public CDC  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMetaFileDC::CMetaFileDC](../Topic/CMetaFileDC::CMetaFileDC.md)|`CMetaFileDC` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMetaFileDC::Close](../Topic/CMetaFileDC::Close.md)|장치 컨텍스트를 닫고 메타 파일 핸들을 만듭니다.|  
|[CMetaFileDC::CloseEnhanced](../Topic/CMetaFileDC::CloseEnhanced.md)|확장 메타 파일 디바이스 컨텍스트를 닫고는 확장 메타 파일 핸들을 만듭니다.|  
|[CMetaFileDC::Create](../Topic/CMetaFileDC::Create.md)|Windows 메타 파일 디바이스 컨텍스트를 만들고이에 연결 된 `CMetaFileDC` 개체입니다.|  
|[CMetaFileDC::CreateEnhanced](../Topic/CMetaFileDC::CreateEnhanced.md)|확장 형식 메타 파일을 메타 파일 디바이스 컨텍스트를 만듭니다.|  
  
## 설명  
 Windows 메타 파일을 구현 하려면 먼저 만들는 `CMetaFileDC` 개체입니다.  호출의 `CMetaFileDC` 생성자를 다음 호출의  [만들기](../Topic/CMetaFileDC::Create.md) Windows 메타 파일 디바이스 컨텍스트를 만들고이를 연결 하는 멤버 함수는 `CMetaFileDC` 개체.  
  
 다음으로 보내기는 `CMetaFileDC` 개체 시퀀스를 `CDC` 하려는 GDI 명령을 재생 하려면.  같은 출력을 만드는 GDI 명령만 `MoveTo` 및 `LineTo`를 사용할 수 있습니다.  
  
 메타 파일에 원하는 명령을 보낸 후 호출 하는  **닫기** 메타 파일 디바이스 컨텍스트를 닫고 메타 파일 핸들을 반환 하는 멤버 함수를.  다음 폐기는 `CMetaFileDC` 개체입니다.  
  
 [CDC::PlayMetaFile](../Topic/CDC::PlayMetaFile.md) 다음 메타 파일 핸들 메타 파일을 반복적으로 재생할 수 있습니다.  메타 파일에는 Windows 함수에 의해 같이 조작할 수 있습니다  [CopyMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183480), 메타 파일을 디스크에 복사 합니다.  
  
 메타 파일 더 이상 필요 하지 않으면 메모리에서 삭제 된  [DeleteMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183537) Windows 함수.  
  
 수도 `CMetaFileDC` 처리할 수 있도록 개체 모두 출력 호출 및 GDI 호출 특성 같은 `GetTextExtent`.  이러한 메타 파일 더 유연 하며 더 자주 호출 하 고 출력 특성의 혼합으로 구성 되는 일반 GDI 코드를 쉽게 다시 사용할 수 있습니다.  `CMetaFileDC` 클래스는 두 개의 장치 컨텍스트에서 상속 `m_hDC` 및 `m_hAttribDC`에서 `CDC`.  `m_hDC` 장치 컨텍스트를 모두 처리  [CDC](../../mfc/reference/cdc-class.md) GDI 호출을 출력 하는 `m_hAttribDC` 장치 컨텍스트를 모두 처리 `CDC` GDI 특성 호출.  같은 장치에 일반적으로 이러한 두 장치 컨텍스트를 참조 하십시오.  경우 `CMetaFileDC`, DC 특성을 설정  **NULL** 기본적으로.  
  
 화면, 프린터 또는 장치 이외의 메타 파일을 가리키도록 다음 호출 하는 두 번째 디바이스 컨텍스트를 만들도록는 `SetAttribDC` 새 디바이스 컨텍스트와 연결 하는 멤버 함수 `m_hAttribDC`.  GDI 호출에 대 한 정보는 이제 수 지시 새 `m_hAttribDC`.  출력 GDI 호출 하기 위해 이동할 `m_hDC`, 메타 파일을 나타냅니다.  
  
 에 대 한 자세한 내용은 `CMetaFileDC`를 참조 하십시오  [장치 컨텍스트](../../mfc/device-contexts.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CMetaFileDC`  
  
## 요구 사항  
 **헤더:**  afxext.h  
  
## 참고 항목  
 [CDC 클래스](../../mfc/reference/cdc-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)