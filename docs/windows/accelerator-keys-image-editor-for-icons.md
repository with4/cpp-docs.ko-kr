---
title: 액셀러레이터 키 (아이콘에 대 한 이미지 편집기) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
dev_langs:
- C++
helpviewer_keywords:
- accelerator keys
- Image editor [C++], accelerator keys
ms.assetid: add37861-3e17-4a6f-89e8-46df12e74a90
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 80ab38a73a142d3ad9f80767ffe8cc8e29b0f7c6
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650929"
---
# <a name="accelerator-keys-image-editor-for-icons"></a>액셀러레이터 키(아이콘에 대한 이미지 편집기)
다음은 기본적으로 키에 바인딩된 이미지 편집기 명령에 대 한 액셀러레이터 키입니다. 액셀러레이터 키를 변경 하려면 클릭 **옵션** 에 **도구** 메뉴를 선택한 후 **키보드** 아래를 **환경** 폴더. 자세한 내용은 [바로 가기 키 식별 및 사용자 지정](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio)을 참조하세요.  
  
> [!NOTE]
>  대화 상자에서 사용할 수 있는 옵션과 메뉴 명령의 이름 및 위치는 실제 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
|명령|키|설명|  
|-------------|----------|-----------------|  
|Image.AirBrushTool|**Ctrl** + **A**|선택한 크기와 색을 사용 하 여에 어 브러시를 사용 하 여 그립니다.|  
|이미지.브러시도구|**Ctrl** + **B**|선택한 모양, 크기 및 색의 브러시로 그립니다.|  
|Image.CopyAndOutlineSelection|**Ctrl** + **Shift** + **U**|현재 선택한 항목의 복사본을 만들고 윤곽선을 그립니다. 배경색은 현재 선택 영역에 포함 되 면 제외 됩니다 있다면 [투명 한](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md) 선택 합니다.|  
|이미지.불투명하게그리기|**Ctrl** + **J**|현재 선택 하거나 만듭니다 [불투명 또는 투명](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)합니다.|  
|이미지.타원도구|**Ctrl** + **P**|선택한 선 두께 및 색을 사용 하 여 타원을 그립니다.|  
|Image.EraserTool|**Ctrl** + **Shift** + **I**|현재 배경색) (사용 하 여 이미지의 일부를 지웁니다.|  
|이미지.채워진타원도구윤곽선없음|**Ctrl** + **Shift** + **Alt** + **P**|채워진 타원을 그립니다|  
|이미지.채워진사각형도구윤곽선없음|**Ctrl** + **Shift** + **Alt** + **R**|채워진 사각형을 그립니다|  
|Image.FilledRoundRectangleTool|**Ctrl** + **Shift** + **Alt** + **W**|모퉁이가 둥근 채워진 사각형을 그립니다.|  
|이미지.채우기도구|**Ctrl** + **F**|영역을 채웁니다.|  
|이미지.좌우대칭|**Ctrl** + **H**|이미지나 선택 영역을 좌우 대칭 이동합니다.|  
|이미지.상하대칭|**Shift**+ **Alt** + **H**|이미지나 선택 영역을 상하 대칭 이동합니다.|  
|이미지.더큰브러시|**Ctrl** + **=**|브러시 크기를 각 방향마다 1픽셀씩 늘립니다. 브러시 크기를 늘리려면 이 표의 이미지.더작은브러시를 참조하십시오.|  
|이미지.선도구|**Ctrl** + **L**|선택한 모양, 크기 및 색으로 직선을 그립니다.|  
|이미지.확대도구|**Ctrl** + **M**|활성화 합니다 **Magnify** 이미지의 특정 부분을 확대할 수 있는 도구입니다.|  
|이미지.확대|**Ctrl** + **Shift** + **M**|현재 확대 비율과 1:1 비율 사이를 전환합니다.|  
|이미지.새이미지형식|**삽입**|시작 합니다 [새로 만들기 \<장치 > 이미지 형식 대화 상자](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md) 만들 수 있는 다른 이미지 형식의 이미지를 사용 하 여 합니다.|  
|이미지.다음색|**Ctrl** + **]**<br /><br /> 또는<br /><br /> **Ctrl** + **오른쪽 화살표**|그리기 전경색을 다음 색상표 색으로 변경합니다.|  
|이미지.다음오른쪽색|**Ctrl** + **Shift** + **]**<br /><br /> 또는<br /><br /> **Shift** + **Ctrl** + **오른쪽 화살표**|그리기 배경색을 다음 색상표 색으로 변경합니다.|  
|이미지.채워진타원도구윤곽선있음|**Shift** + **Alt** + **P**|윤곽선이 있는 채워진 타원을 그립니다.|  
|이미지.채워진사각형도구윤곽선있음|**Shift** + **Alt** + **R**|윤곽선이 있는 채워진 사각형을 그립니다.|  
|Image.OutlinedRoundRectangleTool|**Shift** + **Alt** + **W**|윤곽선으로 채워진 둥근 사각형을 그립니다|  
|이미지.연필도구|**Ctrl** + **I**|단일 픽셀 연필을 사용하여 그립니다|  
|이미지.이전색|**Ctrl** + **[**<br /><br /> 또는<br /><br /> **Ctrl** + **왼쪽 화살표**|그리기 전경색을 이전 색상표 색으로 변경합니다.|  
|이미지.이전오른쪽색|**Ctrl** + **Shift** + **[**<br /><br /> 또는<br /><br /> **Shift** + **Ctrl** + **왼쪽 화살표**|그리기 배경색을 이전 색상표 색으로 변경합니다.|  
|이미지.사각형선택도구|**Shift** + **Alt** + **S**|이동, 복사 또는 편집할 이미지의 사각형 부분을 선택 합니다.|  
|이미지.사각형도구|ATL + R|선택한 선 두께 색으로 사각형을 그립니다.|  
|이미지.90도회전|**Ctrl** + **Shift** + **H**|이미지나 선택 영역을 90도 회전합니다.|  
|이미지.모퉁이가둥근사각형도구|**Alt** + **W**|선택한 선 두께 및 색으로 둥근 사각형을 그립니다.|  
|이미지.모눈표시|**Ctrl** + **Alt** + **S**|픽셀 모눈 (선택 하거나 선택 취소 합니다 **픽셀 모눈** 옵션을 [모눈 설정 대화 상자](../windows/grid-settings-dialog-box-image-editor-for-icons.md)).|  
|이미지.바둑판식모눈표시|**Ctrl** + **Shift** + **Alt** + **S**|바둑판식 모눈 (선택 하거나 선택 취소 합니다 **바둑판식 모눈** 옵션을 [모눈 설정 대화 상자](../windows/grid-settings-dialog-box-image-editor-for-icons.md)).|  
|이미지.작은브러시|**Ctrl** + **.** (마침표)|감소 된 **브러시** 하나의 픽셀 크기입니다. (이 표의 이미지.더큰브러시 및 이미지.더작은브러시 참조).|  
|이미지.더작은브러시|**Ctrl**  +  **-** (빼기)|브러시 크기를 각 방향마다 1픽셀씩 줄입니다. 브러시 크기를 다시 확장하려면 이 표의 이미지.더큰브러시를 참조하십시오.|  
|이미지.텍스트도구|**Ctrl** + **T**|열립니다는 [텍스트 도구 대화 상자](../windows/text-tool-dialog-box-image-editor-for-icons.md)합니다.|  
|Image.UseSelectionAsBrush|**Ctrl** + **U**|현재 선택 사항을 브러시로 사용하여 그립니다.|  
|이미지.확대|**Ctrl** + **Shift** + **합니다.** (마침표)<br /><br /> 또는<br /><br /> **Ctrl** + **위쪽 화살표**|현재 보기 비율을 늘립니다.|  
|이미지.축소|**Ctrl** + **,** (쉼표)<br /><br /> 또는<br /><br /> **Ctrl** + **아래쪽 화살표**|현재 보기 비율을 줄입니다.|  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [아이콘에 대한 이미지 편집기](../windows/image-editor-for-icons.md)