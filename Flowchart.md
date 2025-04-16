```mermaid
flowchart LR

    %% Define custom node styles (no trailing semicolons):
    classDef illicit fill:#FFCCCC,stroke:#FF5555,stroke-width:2px,color:#000
    classDef licit fill:#CCFFCC,stroke:#33CC33,stroke-width:2px,color:#000
    classDef blue fill:#CCE5FF,stroke:#3399FF,stroke-width:2px,color:#000
    classDef pipeline fill:#FFFFFF,stroke:#666,stroke-width:2px,rx:10,ry:10,color:#000

    %% LEFT COLUMN: Inputs
    subgraph sInputs [Inputs]
      direction TB

      %% known_graph: 6 nodes (mix of licit/illicit)
      subgraph known_graph ["known_graph"]
        direction TB
        K1[licit]:::licit
        K2[illicit]:::illicit
        K3[licit]:::licit
        K4[illicit]:::illicit
        K5[licit]:::licit
        K6[illicit]:::illicit

        K1 --- K2
        K2 --- K3
        K3 --- K4
        K4 --- K5
        K5 --- K6
        K6 --- K1
        K2 --- K5
      end

      %% unknown_graph: 4 blue nodes in a square/diamond
      subgraph unknown_graph ["unknown_graph"]
        direction TB
        U1[Unknown]:::blue
        U2[Unknown]:::blue
        U3[Unknown]:::blue
        U4[Unknown]:::blue
        U5[Unknown]:::blue
        U6[Unknown]:::blue
        U7[Unknown]:::blue
        U8[Unknown]:::blue
        U9[Unknown]:::blue

        U1 --- U2
        U2 --- U3
        U3 --- U4
        U4 --- U1
        U1 --- U3
        U2 --- U4
        U5 --- U9
        U8 --- U5
        U9 --- U7
        U4 --- U9
        U7 --- U5
        U2 --- U6
      end
    end

    %% MIDDLE: Pipeline node (no emojis, just text)
    pipeline_node[Pipeline]:::pipeline

    %% RIGHT COLUMN: Outputs
    subgraph sOutputs [Outputs]
      direction TB

      %% unknown_pred_illicit: red nodes
      subgraph unknown_pred_illicit ["unknown_pred_illicit"]
        direction TB
        I0[illicit]:::illicit
        I1[illicit]:::illicit
        I2[illicit]:::illicit
        I3[illicit]:::illicit

        I0 --- I1
        I1 --- I2
        I0 --- I2
        I3 --- I1
      end

      %% unknown_pred_licit: green nodes
      subgraph unknown_pred_licit ["unknown_pred_licit"]
        direction TB
        L0[licit]:::licit
        L1[licit]:::licit
        L2[licit]:::licit
        L3[licit]:::licit
        L4[licit]:::licit

        L0 --- L1
        L0 --- L2
        L2 --- L3
        L1 --- L3
        L4 --- L2
      end
    end

    %% Connections (directional flow)
    sInputs --> pipeline_node
    pipeline_node --> sOutputs

    %% Style the links
    linkStyle default stroke:#888,stroke-width:1.5px