# nats-streaming-server-embedded

![Build][Build-shield] 
[![Maintainable][Maintainable-image]][Maintainable-Url]
[![Coverage][Coverage-image]][Coverage-Url]
![Central][Central-shield] 
![Tag][Tag-shield]
![Issues][Issues-shield] 
![Commit][Commit-shield] 
![Size][Size-shield] 
![Dependency][Dependency-shield]
![License][License-shield]
![Label][Label-shield]

[License-Url]: https://www.apache.org/licenses/LICENSE-2.0
[Build-Status-Url]: https://travis-ci.org/YunaBraska/nats-streaming-server-embedded
[Build-Status-Image]: https://travis-ci.org/YunaBraska/nats-streaming-server-embedded.svg?branch=master
[Coverage-Url]: https://codecov.io/gh/YunaBraska/nats-streaming-server-embedded?branch=master
[Coverage-image]: https://img.shields.io/codecov/c/github/YunaBraska/nats-streaming-server-embedded?style=flat-square
[Maintainable-Url]: https://codeclimate.com/github/YunaBraska/nats-streaming-server-embedded/maintainability
[Maintainable-image]: https://img.shields.io/codeclimate/maintainability/YunaBraska/nats-streaming-server-embedded?style=flat-square
[Javadoc-url]: http://javadoc.io/doc/berlin.yuna/nats-streaming-server-embedded
[Javadoc-image]: http://javadoc.io/badge/berlin.yuna/nats-streaming-server-embedded.svg
[Gitter-Url]: https://gitter.im/nats-streaming-server-embedded/Lobby
[Gitter-image]: https://img.shields.io/badge/gitter-join%20chat%20%E2%86%92-brightgreen.svg

[Dependency-shield]: https://img.shields.io/librariesio/github/YunaBraska/nats-streaming-server-embedded?style=flat-square
[Tag-shield]: https://img.shields.io/github/v/tag/YunaBraska/nats-streaming-server-embedded?style=flat-square
[Central-shield]: https://img.shields.io/maven-central/v/berlin.yuna/nats-streaming-server-embedded?style=flat-square
[Size-shield]: https://img.shields.io/github/repo-size/YunaBraska/nats-streaming-server-embedded?style=flat-square
[Issues-shield]: https://img.shields.io/github/issues/YunaBraska/nats-streaming-server-embedded?style=flat-square
[License-shield]: https://img.shields.io/github/license/YunaBraska/nats-streaming-server-embedded?style=flat-square
[Commit-shield]: https://img.shields.io/github/last-commit/YunaBraska/nats-streaming-server-embedded?style=flat-square
[Label-shield]: https://img.shields.io/badge/Yuna-QueenInside-blueviolet?style=flat-square
[Build-shield]: https://img.shields.io/travis/YunaBraska/nats-streaming-server-embedded/master?style=flat-square

### Description
Embedded [Nats streaming server](https://github.com/nats-io/nats-streaming-server) for testing which contains the original [Nats streaming server](https://github.com/nats-io/nats-streaming-server) 

### Usage
* One annotation to setup the powerful [Nats streaming server](https://github.com/nats-io/nats-streaming-server)
```java
@SpringBootTest
@RunWith(SpringRunner.class)
@EnableNatsServer(port = 4222, natsServerConfig = {"user:admin", "pass:admin"})
public class SomeTest {
    [...]
}
```
* See [NatsServerConfig](https://github.com/YunaBraska/nats-streaming-server-embedded/blob/master/src/main/java/berlin/yuna/natsserver/config/NatsServerConfig.java) class for available properties
* @EnableNatsServer is also reading spring config
* @EnableNatsServer parameters are overwriting the spring properties
```yaml
nats:
  server:
    hb_fail_count: 3
```

```properties
nats.server.hb_fail_count=3
```

* See [NatsServerSourceConfig](https://github.com/YunaBraska/nats-streaming-server-embedded/blob/master/src/main/java/berlin/yuna/natsserver/config/NatsServerSourceConfig.java) class for optional available nats version configuration
```yaml
nats:
  source:
    mac: "https://nats-mac.zip"
    linux: "https://nats-linux.zip"
    solaris: "https://nats-solaris.zip"
    windows: "https://nats-windows.zip"
    default: "file://${user.dir}/nats-foo-bar.zip"
```

```
                                                             .,,.                                                             
                                                              ,/*.                                                            
                                                               *(/.                                                           
                                                               .(#*..                                                         
                                                               ,(#/..                                                         
                                                              ,(#(*..                                                         
                                                             ,/###/,,                                                         
                                                          ..*(#(**(((*                                                        
                                                         ,((#(/. ./##/.                                                       
                                                        ./##/,   ,(##/.                                                       
                                                        ,(((,   ./###*.                                                       
                                                        ,///.  ,(##//.                                                        
                                                         ,**,,/(#(*                                                           
                                                            ,(#(*.                                                            
                                                          ..*((*.                                                             
                                                          ,,((,                                                               
                                                          ..//.                                                               
                                                            .,.                                                               
                                                         .....,.........                                                      
                                            ..,**///(((((##############(((((((//*,..                                          
                                       .*//((#######################################((/*,.                                    
                                    ,/(###################################################/*..                                
                                .,,(########################################################((/.                              
                                ,((###########################################################(/.                             
                              .(#################################################################*                            
                             .(#.###############################################################*                           
                            ./#....###########################################################...,                          
                            .(#.....########################################################.....*                          
                            ,#.........##################################################.........#/.                         
                            *#...##.........##########################################........#...##(((//*,.                  
                            ,#..####...#............##########################..........#...####..........##/..               
                            ,#..####..###..............................................###..####...........##**               
                            .(#.#####.###....##..................................##...####.#####..#/,,,,/##..((.              
                             ,#..####..####..###....###..................####...###...###..####..#/.    .(#..((.              
                             ./#.#####.#####.####...####................#####..####.#####.#####.,    ./#..#//.              
                              ,#.#####.#####.#####..####................#####.####..##########..#/.    ,##.,,               
                               *#..######################..............#######################.#(.  .//#..##*                 
                                *##.#####################..............#####################..#(,.,/###..#(,                  
                                 **#######################............#####################...#####....##*.                   
                                   ,(#.#####################.........####################.........###//,                      
                                    *########################......######################..#######(/,..                       
                                     ,(#######################....########.############..#/,....                              
                                      ./###############.#####......#####.#############.##/**,,,.                              
                                        ,((#.###########..###......##...###########...#(/*********,.                          
                                         ,,(#.###########..............###########..###/************,..                       
                                            *(#.############.........###########..##//******************,.                    
                                              ,/#############......###########.##(/***********************,.                  
                                                .*((########.........#####.###/,...,,,,,,*******************,..               
                                                  ,,/########......#####.##((*.         ....,,,,*************,,.              
                                                     .,(##.............##(*.....,,,,,,,,,,,,,,,,,**************,              
                                                        .*###........##(/***********************************,..               
                                                            *(#...###/************************************,.                  
                                                             *(#.##//************************************,.                   
                                                              ./(*.,,********************************,,.                      
                                                                       .,************************,..                          
                                                                           ...,,,,******,,,,...                           
```