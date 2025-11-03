# Prompt Protocols

> Structured prompt templates for AI-assisted scientific software development

This repository provides prompt engineering templates and guidance for scientific researchers who write software as part of their research. Based on "Ten Simple Rules for AI-Assisted Coding in Science" by Bridgeford et al. (2025), these templates help you develop better prompts for AI coding assistants, leading to more reliable and scientifically sound code.

## Quick Start

1. **Clone the repository** to a central location:
   ```bash
   git clone git@github.com:sscivier/prompt-protocols.git ~/path/to/tools/prompt-protocols
   ```

2. **Symlink into your project**:
   ```bash
   cd ~/path/to/your-project/.github
   ln -s ~/path/to/tools/prompt-protocols/prompts ./prompts
   ln -s ~/path/to/tools/prompt-protocols/assessment ./assessment
   ```

3. **Start using templates** - see [SETUP.md](SETUP.md) for detailed instructions.

## What's Inside

- **[Prompt Templates](prompts/TEMPLATES-INDEX.md)** - Structured templates for domain research, problem framing, solution specification, test design, code review, and more
- **[Assessment Tools](assessment/prompt-assessment.md)** - Framework for evaluating prompt quality and effectiveness, that can be given to an AI assistant or used as a self-check
- **[Reference Guide](ten-simple-rules-reference.md)** - Shortened version of "Ten Simple Rules for AI-Assisted Coding in Science"

## Example Workflow

Suppose you need to implement a data processing function but aren't sure about domain standards:

1. **Research**: Use `01-domain-research.md` to understand standard approaches
2. **Frame**: Use `02-problem-framing.md` to architect your solution
3. **Specify**: Use `05-solution-specification.md` to define clear requirements
4. **Test**: Use `06-test-design.md` to specify test cases before implementation
5. **Implement**: Use `implementation.md` to create your final prompt
6. **Assess**: Have AI review your prompt against `prompt-assessment.md`
7. **Revise**: Incorporate AI feedback into your prompt
8. **Run**: Run prompt with your AI assistant
9. **Review**: Carefully review all AI-generated code, use `08-code-review.md`, `09-code-refinement.md`, and `10-debugging.md` as appropriate

See [TEMPLATES-INDEX.md](prompts/TEMPLATES-INDEX.md) for all available templates and detailed usage guidance.

## Setup

Full setup instructions: [SETUP.md](SETUP.md)

Key points:
- Clone once to a central location
- Symlink into individual projects
- Updates propagate automatically across all projects

## Contributing

We welcome contributions from researchers! See [CONTRIBUTING.md](CONTRIBUTING.md) for:
- How to improve templates
- Adding domain-specific examples
- Contribution workflow and guidelines

Please read our [Code of Conduct](CODE_OF_CONDUCT.md) before contributing.

## Citation

To cite the Bridgeford *et al.* (2025) paper, use:

```bibtex
@misc{bridgeford2025simplerulesaiassistedcoding,
      title={Ten Simple Rules for AI-Assisted Coding in Science}, 
      author={Eric W. Bridgeford and Iain Campbell and Zijao Chen and Zhicheng Lin and Harrison Ritz and Joachim Vandekerckhove and Russell A. Poldrack},
      year={2025},
      eprint={2510.22254},
      archivePrefix={arXiv},
      primaryClass={cs.SE},
      url={https://arxiv.org/abs/2510.22254}, 
}
```

## License

Apache-2.0. See [LICENSE](LICENSE) for details.
