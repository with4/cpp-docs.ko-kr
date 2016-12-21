---
title: "Windows 스토어 응용 프로그램에서 C++ AMP 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 85577298-2c28-4209-9470-eb21048615db
caps.latest.revision: 14
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows 스토어 응용 프로그램에서 C++ AMP 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에 C\+\+ AMP\(C\+\+ Accelerated Massive Parallelism\)를 설치하여 GPU\(그래픽 처리 장치\) 또는 다른 연산 가속기를 수행할 수 있습니다.  그러나, C\+\+ AMP는 Windows Runtime 형식으로 직접 작업하기 위한 API를 제공하지 않으며, Windows 런타임은 C\+\+ AMP에 대한 래퍼를 제공하지 않습니다.  코드에 본인이 직접 만든 형식을 포함하여 Windows 런타임 형식을 사용할 경우 C\+\+ AMP와 호환되는 형식으로 변환해야 합니다.  
  
## 성능 고려 사항  
 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 앱을 만들기 위해 [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)]\([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]\)을 사용하는 경우 C\+\+ AMP에 사용할 데이터에 대해 POD\(Plain\-Old\-Data\) 형식과 함께 연속 저장소\(예: `std::vector` 또는 C 스타일 배열\)를 사용하는 것이 좋습니다.  이렇게 하면 마샬링을 수행할 필요가 없기 때문에 비POD 형식 또는 Windows RT 컨테이너를 사용해서 더 높은 성능을 얻을 수 있습니다.  
  
 C\+\+ AMP 커널에서 이 방식으로 저장된 데이터에 액세스하려면 `std::vector` 또는 `concurrency::array_view`의 배열 저장소를 래핑한 후 `concurrency::parallel_for_each` 루프에서 배열 뷰를 사용합니다.  
  
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
  
## Windows 런타임 형식 마샬링  
 Windows 런타임 API로 작업을 할 때, `Platform::Array<T>^` 와 같은 Windows 런타임 컨테이너에 저장되는 데이터에서 또는 `ref` 키워드나 `value` 키워드를 사용하여 선언되는 클래스 또는 구조체 같은 복잡한 데이터 형식으로 C\+\+ AMP를 사용할 수 있습니다.  이와 같은 경우, C\+\+ AMP에 데이터를 사용할 수 있도록 몇 가지 추가 작업을 수행합니다.  
  
### Platform::Array\<T\>^, 여기서 T는 POD 형식  
 `Platform::Array<T>^`이 발생하고 T가 POD 형식이면 `get` 멤버 함수를 사용하여 내부 저장소에 액세스할 수 있습니다.  
  
```cpp  
Platform::Array<float>^ arr; // Assume that this was returned by a Windows Runtime API  
concurrency::array_view<float, 1> av(arr->Length, &arr->get(0));  
  
```  
  
 T가 POD 형식이 아닌 경우 다음 단원에 설명되어 있는 기술을 사용하여 데이터를 C\+\+ AMP와 함께 사용합니다.  
  
### Windows 런타임 형식: ref 클래스 및 값 클래스  
 C\+\+ AMP는 복잡한 데이터 형식을 지원하지 않습니다.  여기에는 비POD 형식 및 `ref` 키워드 또는 `value` 키워드를 사용하여 선언된 모든 형식이 포함됩니다.  `restrict(amp)` 컨텍스트에 지원되지 않는 형식을 사용하면 컴파일 타임 오류가 생성됩니다.  
  
 지원되지 않는 형식이 발견되면 해당 데이터의 관심 있는 부분을 `concurrency::array` 개체로 복사할 수 있습니다.  C\+\+ AMP가 소비할 수 있도록 데이터를 설정하는 것 외에도 이 수동 복사 방식을 사용하면 데이터 집약성을 극대화하고 사용되지 않는 데이터가 액셀러레이터에 복사되지 않도록 보장하여 성능을 향상시킬 수 있습니다.  AMP 런타임에 힌트를 제공하는 `concurrency::array`의 특별한 형식인 *스테이징 배열*을 사용하여 성능을 개선할 수 있습니다. 배열은 해당 배열과 지정된 가속기의 다른 배열 간의 빈번한 전송에 최적화되어야 합니다.  
  
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
..property int b;  
};  
  
// Some other file  
std::vector<pixel_color^> pixels (256);   
  
for(pixel_color ^pixel : pixels)   
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
  red_vec[i] = pixels[i]->r; blue_vec[i] = pixels[i]->b;  
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
  
## 참고 항목  
 [C\+\+를 사용하여 첫 Windows 스토어 앱 만들기](http://go.microsoft.com/fwlink/p/?LinkId=249073)   
 [C\+\+로 Windows Runtime 구성 요소 만들기](http://go.microsoft.com/fwlink/p/?LinkId=249076)