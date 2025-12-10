# Robotics Internal Developer Platform (IDP) - Reference Implementation

**🔗 Repository:** https://github.com/akshaymittal143/Robotics-Internal-Developer-Platform-IDP

This repository contains the reference implementation and reproducibility artifacts for the paper:

**"A Cloud-Native Internal Developer Platform for Autonomous Robot Fleets"**  
📄 *Accepted at ICCA 2025 (International Conference on Computing and Artificial Intelligence)*  
👥 *Authors: Akshay Mittal, Krishna Kandi*

## Repository Structure

```
├── README.md                    # This file
├── crds/                       # Custom Resource Definitions
│   ├── robotprofile.yaml      # RobotProfile CRD
│   ├── fleetconfig.yaml       # FleetConfiguration CRD  
│   ├── roboticsapp.yaml       # RoboticsApplication CRD
│   └── modeldeployment.yaml   # ModelDeployment CRD
├── controllers/               # Kubernetes Controllers
│   ├── robotics-operator/     # Main Robotics Operator
│   └── examples/             # Sample controller implementations
├── manifests/                # Sample GitOps manifests
│   ├── fleet-configs/        # Fleet configuration examples
│   ├── model-deployments/    # ML model deployment examples
│   └── applications/         # Robotics application examples
├── charts/                   # Helm charts for deployment
│   ├── robotics-idp/         # Core IDP platform chart
│   └── monitoring/           # Observability stack
└── docs/                     # Additional documentation
    ├── architecture.md       # Detailed architecture guide
    ├── quickstart.md         # Getting started guide
    └── examples/             # Usage examples and tutorials
```

## Quick Start

### Prerequisites
- Kubernetes cluster (v1.24+)
- kubectl configured
- Helm 3.x
- ArgoCD or Flux (GitOps operator)

### Installation

1. **Install Custom Resource Definitions**
   ```bash
   kubectl apply -f crds/
   ```

2. **Deploy the Robotics Operator**
   ```bash
   helm install robotics-idp charts/robotics-idp/
   ```

3. **Apply Sample Configurations**
   ```bash
   kubectl apply -f manifests/fleet-configs/
   ```

## Key Components

### Custom Resource Definitions (CRDs)
- **RobotProfile**: Defines physical robot capabilities and constraints
- **FleetConfiguration**: Global fleet parameters and policies  
- **RoboticsApplication**: Deployable software components
- **ModelDeployment**: AI/ML model lifecycle management

### Controllers
- **Robotics Operator**: Core controller implementing the reconciliation logic
- **Hardware-aware Scheduler**: Ensures optimal workload placement
- **Model Serving Controller**: Manages KServe integration

## Usage Examples

See the `docs/examples/` directory for detailed usage scenarios including:
- Canary deployment of perception models
- Fleet-wide configuration updates
- Hardware-aware application scheduling
- Monitoring and observability setup

## Contributing

This is a reference implementation supporting academic research. For contributions or questions, please refer to the paper's contact information.

## Citation

If you use this code in your research, please cite:

```bibtex
@inproceedings{mittal2025robotics,
  title={A Cloud-Native Internal Developer Platform for Autonomous Robot Fleets},
  author={Mittal, Akshay and Kandi, Krishna},
  booktitle={2025 International Conference on Computing and Artificial Intelligence (ICCA)},
  year={2025},
  organization={IEEE}
}
```

**Paper Status:** ✅ **Accepted at ICCA 2025**

## License

This project is licensed under the MIT License - see the LICENSE file for details.
