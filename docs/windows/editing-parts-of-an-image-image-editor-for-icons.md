---
title: 이미지 (아이콘에 대 한 이미지 편집기)의 일부 편집 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Image editor [C++], editing images
- Clipboard [C++], pasting
- images [C++], editing
- images [C++], deleting selected parts
- images [C++], copying selected parts
- images [C++], moving selected parts
- images [C++], dragging and replicating selected parts
- images [C++], pasting into
- graphics [C++], editing
ms.assetid: ff4f5fef-71a4-4fd8-825e-049399fed391
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1880853c63a236e824f9b59156181dccb2bba819
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647448"
---
# <a name="editing-parts-of-an-image-image-editor-for-icons"></a>이미지의 일부 편집(아이콘에 대한 이미지 편집기)
표준 편집 작업을 수행할 수 있습니다-잘라내기, 복사, 해제 및 이동-에 [선택](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)의 일부 또는 전체 이미지 선택 인지, 합니다. 때문에 **이미지** 편집기를 사용 합니다 **Windows 클립보드**, 간에 이미지를 전송할 수 있습니다는 **이미지** 편집기 및 Windows 용 응용 프로그램.  
  
 또한 일부 또는 전체 이미지를 포함 하는지 여부를 선택 항목을 조정할 수 있습니다.  
  
### <a name="to-cut-the-current-selection-and-move-it-to-the-clipboard"></a>현재 선택 영역을 잘라내어 클립보드에 이동 하려면  
  
1.  클릭 **잘라내기** 에 **편집** 메뉴.  
  
### <a name="to-copy-the-selection"></a>선택 영역 복사  
  
1.  크기 조정 핸들 제외 하 고에 선택 테두리 내에서 또는 어디서 나 포인터를 놓습니다.  
  
2.  누른 합니다 **Ctrl** 키를 새 위치로 선택 항목을 끕니다. 원래 선택 항목의 영역 변경 되지 않습니다.  
  
3.  선택 영역에 현재 위치에 있는 이미지를 복사 하려면 선택 커서 바깥쪽을 클릭 합니다.  
  
### <a name="to-paste-the-clipboard-contents-into-an-image"></a>에 이미지에 클립보드 내용 붙여넣기  
  
1.  **편집할** 메뉴 선택 **붙여넣기**합니다.  
  
     클립보드 내용을 선택 테두리가 창의 왼쪽 위 모퉁이에 나타납니다.  
  
2.  선택 영역 테두리 내에 포인터를 배치 하 고 이미지를 이미지에 원하는 위치로 끕니다.  
  
3.  새 위치에 이미지를 고정 된 선택 테두리 외부를 클릭 합니다.  
  
### <a name="to-delete-the-current-selection-without-moving-it-to-the-clipboard"></a>클립보드로 이동 하지 않고 현재 선택 영역을 삭제 하려면  
  
1.  **편집할** 메뉴 선택 **삭제**합니다.  
  
     선택 영역의 원래 현재 배경색으로 채워집니다.  
  
    > [!NOTE]
    >  액세스할 수 있습니다 합니다 **잘라내기**, **복사**를 **붙여넣기**, 및 **삭제** 명령을 마우스 오른쪽 단추로 클릭 하 여는 **리소스 뷰** 창입니다.  
  
### <a name="to-move-the-selection"></a>선택 항목  
  
1.  크기 조정 핸들 제외 하 고에 선택 테두리 내에서 또는 어디서 나 포인터를 놓습니다.  
  
2.  선택 항목을 새 위치로 끕니다.  
  
3.  새 위치에 있는 이미지에서 선택 영역 앵커와 선택 테두리 바깥쪽을 클릭 합니다.  
  
 선택 하 여 드로잉에 대 한 자세한 내용은 참조 하세요. [사용자 지정 브러시 만들기](../windows/creating-a-custom-brush-image-editor-for-icons.md)합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)   
 [그래픽 리소스 편집](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [아이콘에 대한 이미지 편집기](../windows/image-editor-for-icons.md)