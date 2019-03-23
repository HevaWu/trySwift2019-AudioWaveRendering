# AudioRender
Demonstration application for audio waveform rendering on iOS

Reference: 
- fork from https://github.com/ekkotech/AudioRender
- https://developer.apple.com/documentation/accelerate

## How To Check
There are some branches in this repository. You could check the steps by the repository's name. 
Here are the branch list:
- [render/fill](https://github.com/HevaWu/trySwift2019-AudioWaveRendering/tree/render/fill)
- [render/linkline](https://github.com/HevaWu/trySwift2019-AudioWaveRendering/tree/render/linkline)
- [accelerate/merge](https://github.com/HevaWu/trySwift2019-AudioWaveRendering/tree/accelerate/merge)
- [accelerate/downsample](https://github.com/HevaWu/trySwift2019-AudioWaveRendering/tree/accelerate/downsample)
- [accelerate/pointArray](https://github.com/HevaWu/trySwift2019-AudioWaveRendering/tree/accelerate/pointArray)
- [accelerate/calPeak](https://github.com/HevaWu/trySwift2019-AudioWaveRendering/tree/accelerate/calcPeak)
- [enable/multiReader](https://github.com/HevaWu/trySwift2019-AudioWaveRendering/tree/enable/multiReader)

### Some results:
#### 1.RenderMode: linkLines  
```
Strategy: Max Value, 
Using Accelerate: Ds: N, Merge: N, Calc Peak: N, BuildPoints: N 
Multi-reader: No 
Num Readers: 1 
Render style: Link Lines

// ------  1 st running ------ 

File read:  		0.05706641500000842
Downsample:  		0.6361131040030159
Merge:  		1.883300137706101e-05
Peak calc:  		5.129000783199444e-06
Point array:  		0.0006814059997850563
Total processing: Ds: 8887 		0.7003818039993348
Build path:  		0.0002812670027196873
Draw:  		3.743799970834516e-05
Total render: (wave) 		0.0003440969994699117


File read:  		0.0025095279997913167
Downsample:  		0.03643889900195063
Merge:  		4.418001481099054e-06
Peak calc:  		5.2579998737201095e-06
Point array:  		0.0006791359992348589
Total processing: Ds: 512 		0.039841473000706173
Build path:  		0.0002485190016159322
Draw:  		1.6120000509545207e-05
Total render: (wave) 		0.0002785969991236925

// -------  2 nd running -------

File read:  		0.012393179000355303
Downsample:  		0.6247476089993143
Merge:  		3.872002707794309e-06
Peak calc:  		5.147001502336934e-06
Point array:  		0.0006268139986786991
Total processing: Ds: 8887 		0.6483811389989569
Build path:  		0.0002608399991004262
Draw:  		2.4777000362519175e-05
Total render: (wave) 		0.00030108599821687676


File read:  		0.0006129680004960392
Downsample:  		0.038357659002940636
Merge:  		4.208999598631635e-06
Peak calc:  		5.4969968914519995e-06
Point array:  		0.0006654630014963914
Total processing: Ds: 512 		0.04005891900305869
Build path:  		0.00025913699937518686
Draw:  		2.5716999516589567e-05
Total render: (wave) 		0.0002966559986816719
```

#### 2.RenderMode: fill  
```
Strategy: Max Value, 
Using Accelerate: Ds: N, Merge: N, Calc Peak: N, BuildPoints: N 
Multi-reader: No 
Num Readers: 1 
Render style: Fill

File read:  		0.05221913700006553
Downsample:  		0.6313178759992297
Merge:  		5.077999958302826e-06
Peak calc:  		4.944002284901217e-06
Point array:  		0.0008613900026830379
Total processing: Ds: 8887 		0.6907518230000278
Build path:  		3.87740001315251e-05
Draw:  		5.1730999985011294e-05
Total render: (wave) 		0.00011932800043723546


File read:  		0.002804493000439834
Downsample:  		0.037659092999092536
Merge:  		4.13400266552344e-06
Peak calc:  		5.4299998737405986e-06
Point array:  		0.0006646780020673759
Total processing: Ds: 512 		0.04135714599760831
Build path:  		2.0273997506592423e-05
Draw:  		2.7313002647133544e-05
Total render: (wave) 		6.426800246117637e-05

```

#### 3.Accelerate: DS data source  

```
// ---- Ds to true

Strategy: Max Value, 
Using Accelerate: Ds: Y, Merge: N, Calc Peak: N, BuildPoints: N 
Multi-reader: No 
Num Readers: 1 
Render style: Fill


File read:  		0.696865717000037
Downsample: af 		0.012217112998769153
Merge:  		7.570000889245421e-06
Peak calc:  		6.741000106558204e-06
Point array:  		0.0009295010022469796
Total processing: Ds: 12460 		0.7213247309991857
Build path:  		5.388000136008486e-05
Draw:  		6.533300256705843e-05
Total render: (wave) 		0.00015728899961686693


File read:  		0.028986162000364857
Downsample: af 		0.0006657429985352792
Merge:  		5.603000317933038e-06
Peak calc:  		6.817001121817157e-06
Point array:  		0.0008708880013728049
Total processing: Ds: 512 		0.030736518998310203
Build path:  		4.165900099906139e-05
Draw:  		3.2033000024966896e-05
Total render: (wave) 		9.208800111082383e-05
```

#### 4.Accelerate: Merge  

```
// -- Merge: True

Strategy: Max Value, 
Using Accelerate: Ds: Y, Merge: Y, Calc Peak: N, BuildPoints: N 
Multi-reader: No 
Num Readers: 1 
Render style: Fill


File read:  		0.5513693709981453
Downsample: af 		0.004690932000812609
Merge: af 		5.0622002163436264e-05
Peak calc:  		5.3290023060981184e-06
Point array:  		0.0006816679997427855
Total processing: Ds: 12460 		0.5665769129991531
Build path:  		4.460999844013713e-05
Draw:  		3.7064997741254047e-05
Total render: (wave) 		0.00011021099999197759


File read:  		0.021798622998176143
Downsample: af 		0.00045203599802334793
Merge: af 		1.2650016287807375e-06
Peak calc:  		5.130998033564538e-06
Point array:  		0.0007164279995777179
Total processing: Ds: 512 		0.023171388998889597
Build path:  		6.69270011712797e-05
Draw:  		2.432200199109502e-05
Total render: (wave) 		0.00010549199942033738
```

#### 5.Accelerate: BuildPoints

```
// BuildPoints: True

Strategy: Max Value, 
Using Accelerate: Ds: Y, Merge: Y, Calc Peak: N, BuildPoints: Y 
Multi-reader: No 
Num Readers: 1 
Render style: Fill


File read:  		0.5444556110014673
Downsample: af 		0.005054999997810228
Merge: af 		1.2764001439791173e-05
Peak calc:  		5.324000085238367e-06
Point array:  		0.0017359660014335532
Total processing: Ds: 12460 		0.5601742340004421
Build path:  		8.477099981973879e-05
Draw:  		6.216300243977457e-05
Total render: (wave) 		0.00020629899881896563


File read:  		0.022301297998637892
Downsample: af 		0.0005183180001040455
Merge: af 		1.1200027074664831e-06
Peak calc:  		5.188998329686001e-06
Point array:  		9.126000804826617e-06
Total processing: Ds: 512 		0.02308740700027556
Build path:  		1.7632002709433436e-05
Draw:  		2.4637000024085864e-05
Total render: (wave) 		5.5529999372083694e-05
```

#### 6.Accelerate: Calc Peak

```
// Calc Peak: True 

Strategy: Max Value, 
Using Accelerate: Ds: Y, Merge: Y, Calc Peak: Y, BuildPoints: Y 
Multi-reader: No 
Num Readers: 1 
Render style: Fill


File read:  		0.5476961109998228
Downsample: af 		0.01089080599922454
Merge: af 		2.1325002308003604e-05
Peak calc:  		1.532700116513297e-05
Point array:  		0.00011465399802546017
Total processing: Ds: 12460 		0.5707270920029259
Build path:  		4.638300015358254e-05
Draw:  		3.883400131599046e-05
Total render: (wave) 		0.00011528400136739947


File read:  		0.024666820998390904
Downsample: af 		0.0005306750026647933
Merge: af 		1.2450000212993473e-06
Peak calc:  		9.489995136391371e-07
Point array:  		9.502000466454774e-06
Total processing: Ds: 512 		0.02537881700118305
Build path:  		3.6890000046696514e-05
Draw:  		2.862000110326335e-05
Total render: (wave) 		8.257999797933735e-05
```

#### 7. Enable Multi-reader

```
// 2 multi-readers

Async file duration: Ds: 12460 0.2951574589969823
Strategy: Max Value, 
Using Accelerate: Ds: Y, Merge: Y, Calc Peak: Y, BuildPoints: Y 
Multi-reader: Yes 
Num Readers: 2 
Render style: Fill


Point array:  		0.0010144500010937918
Build path:  		5.500399856828153e-05
Draw:  		6.499799928860739e-05
Total render: (wave) 		0.0001574790003360249


File read:  		0.021582609999313718
Downsample: af 		0.0006149729997559916
Merge: af 		1.2859964044764638e-06
Peak calc:  		7.060007192194462e-07
Point array:  		1.121199966291897e-05
Total processing: Ds: 512 		0.023416179999912856
Build path:  		2.372900053160265e-05
Draw:  		1.3859000318916515e-05
Total render: (wave) 		5.5828000768087804e-05

// 3 mult-readers

Async file duration: Ds: 12460 0.2140195739993942
Strategy: Max Value, 
Using Accelerate: Ds: Y, Merge: Y, Calc Peak: Y, BuildPoints: Y 
Multi-reader: Yes 
Num Readers: 3 
Render style: Fill


Point array:  		9.147500168182887e-05
Build path:  		3.945299977203831e-05
Draw:  		3.5384000511839986e-05
Total render: (wave) 		0.00010416300210636109


File read:  		0.021210394999798154
Downsample: af 		0.0006495499983429909
Merge: af 		2.038999809883535e-06
Peak calc:  		7.840026228222996e-07
Point array:  		1.076199987437576e-05
Total processing: Ds: 512 		0.02338507699823822
Build path:  		5.521399725694209e-05
Draw:  		3.5211000067647547e-05
Total render: (wave) 		0.00011652000102913007

```
