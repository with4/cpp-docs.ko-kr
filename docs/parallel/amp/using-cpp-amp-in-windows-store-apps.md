---
title: UWP 앱에서 c + + AMP를 사용 하 여 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 85577298-2c28-4209-9470-eb21048615db
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5736c84f21535222de5659780968efd98e1467da
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33696157"
---
# <a name="using-c-amp-in-uwp-apps"></a>UWP 앱에서 c + + AMP를 사용 하 여
GPU (그래픽 처리 장치) 또는 기타 계산 액셀러레이터에서 계산을 수행 하려면 유니버설 Windows 플랫폼 (UWP) 앱에서 c + + AMP (c + + Accelerated Massive Parallelism)를 사용할 수 있습니다. 그러나, C++ AMP는 Windows Runtime 형식으로 직접 작업하기 위한 API를 제공하지 않으며, Windows 런타임은 C++ AMP에 대한 래퍼를 제공하지 않습니다. 코드(본인이 직접 만든 형식 포함)에 Windows 런타임 형식을 사용할 경우 C++ AMP와 호환되는 형식으로 변환해야 합니다.  
  
## <a name="performance-considerations"></a>성능 고려 사항  
 사용 중인 경우 [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] ([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]) 유니버설 Windows 플랫폼 (UWP) 앱을 만들려면 연속 저장소와 함께 일반 이전 데이터 (POD) 형식을 사용 하는 권장-예를 들어 `std::vector` C 스타일 배열 또는-사용 되는 데이터에 대 한 c + + AMP와. 이 마샬링이 없는 발생 하기 때문에 비 POD 형식 또는 Windows RT 컨테이너를 사용 하 여 보다 더 높은 성능을 얻을 수 있습니다.  
  
 이러한 방식으로 저장 된 데이터에 액세스 하는 c + + AMP 커널에 방금 래핑하는 `std::vector` 또는 배열에 저장소는 `concurrency::array_view` 다음에 배열 뷰를 사용 하 여는 `concurrency::parallel_for_each` 루프:  
  
```cpp  
// simple vector addition example  
std::vector<int> data0(1024, 1);
std::vector<int> data1(1024, 2);
std::vector<int> data_out(data0.size(), 0);
  
concurrency::array_view<int, 1> av0(data0.size(), data0);
concurrency::array_view<int, 1> av1(data1.size(), data1);
concurrency::array_view<int, 1> av2(data_out.size(), data2);
  
av2.discard_data();
  
concurrency::parallel_for_each(av0.extent, [=](concurrency::index<1> idx) restrict(amp)  
    {  
        av2[idx] = av0[idx] + av1[idx];  
    });
```  
  
## <a name="marshaling-windows-runtime-types"></a>Windows 런타임 형식 마샬링  
 Windows 런타임 API로 작업을 할 때, `Platform::Array<T>^`와 같은 Windows 런타임 컨테이너에 저장되는 데이터에서 또는 `ref` 키워드나 `value` 키워드를 사용하여 선언되는 클래스 또는 구조체 같은 복잡한 데이터 형식으로 C++ AMP를 사용할 수 있습니다. 이러한 경우 c + + AMP를 데이터를 사용할 수 있도록 몇 가지 추가 작업을 수행 해야 합니다.  
  
### <a name="platformarrayt-where-t-is-a-pod-type"></a>Platform:: array\<T > ^, 여기서 T는 POD 형식  
 발생 하는 `Platform::Array<T>^` 및 T는 POD 형식, 사용 하 여 해당 기본 저장소에 액세스할 수 있습니다는 `get` 멤버 함수:  
  
```cpp  
Platform::Array<float>^ arr; // Assume that this was returned by a Windows Runtime API  
concurrency::array_view<float, 1> av(arr->Length, &arr->get(0));
```  
  
 T POD 형식인 경우 c + + AMP와 데이터를 사용 하려면 다음 섹션에서 설명 하는 방법을 사용 합니다.  
  
### <a name="windows-runtime-types-ref-classes-and-value-classes"></a>Windows 런타임 형식: ref 클래스 및 값 클래스  
 C + + AMP는 복잡 한 데이터 형식을 지원 하지 않습니다. 여기에 비 POD 형식 및 사용 하 여 선언 된 모든 형식을 `ref` 키워드 또는 `value` 키워드입니다. 지원 되지 않는 형식을 사용 하는 경우는 `restrict(amp)` 컨텍스트, 컴파일 타임 오류가 생성 됩니다.  
  
 지원 되지 않는 형식 발생 하면 관심 있는 부분은의 데이터를 복사할 수 있습니다는 `concurrency::array` 개체입니다. 데이터, c + + AMP를 사용할 수 있도록 설정 하는 것 외에도이 수동 복사 방법 또한 고 향상 시킬 수 성능 데이터 집약성을 최대화 하 여 액셀러레이터 키에는 사용 되지 않게 하는 데이터 복사 되지 않습니다 함을 보장 합니다. 사용 하 여 성능이 더욱 향상 시킬 수 있습니다는 *배열 준비*, 특별 한 형태의 변수인 `concurrency::array` 배열 하 고 다른 배열 사이 자주 전송에서 최적화 해야 AMP 런타임이 대 한 힌트를 제공 하는 가속기를 지정된 합니다.  
  
```cpp  
// pixel_color.h  
ref class pixel_color sealed  
{  
public: 
    pixel_color(Platform::String^ color_name, int red, int green, int blue)   
    {  
        name = color_name;  
        r = red;  
        g = green;  
        b = blue;  
    }  
 
    property Platform::String^ name;   
    property int r;  
    property int g;  
    property int b;  
};  
  
// Some other file  
  
std::vector<pixel_color^> pixels (256);
  
for (pixel_color ^pixel : pixels)   
{  
    pixels.push_back(ref new pixel_color("blue", 0, 0, 255));
}  
  
// Create the accelerators  
auto cpuAccelerator = concurrency::accelerator(concurrency::accelerator::cpu_accelerator);
auto devAccelerator = concurrency::accelerator(concurrency::accelerator::default_accelerator);
  
// Create the staging arrays  
concurrency::array<float, 1> red_vec(256, cpuAccelerator.default_view, devAccelerator.default_view);
concurrency::array<float, 1>  blue_vec(256, cpuAccelerator.default_view, devAccelerator.default_view);
  
// Extract data from the complex array of structs into staging arrays.  
concurrency::parallel_for(0, 256, [&](int i)  
    {   
        red_vec[i] = pixels[i]->r;  
        blue_vec[i] = pixels[i]->b;  
    });
  
// Array views are still used to copy data to the accelerator  
concurrency::array_view<float, 1> av_red(red_vec);
concurrency::array_view<float, 1> av_blue(blue_vec);
  
// Change all pixels from blue to red.  
concurrency::parallel_for_each(av_red.extent, [=](index<1> idx) restrict(amp)  
    {  
        av_red[idx] = 255;  
        av_blue[idx] = 0;  
    });
```  
  
## <a name="see-also"></a>참고 항목  
 [C + +를 사용 하 여 첫 번째 UWP 앱 만들기](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)   
 [C + + Windows 런타임 구성 요소 만들기](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)

