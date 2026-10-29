# Validation Checklist

Use this checklist after configuring the VM. Mark an item complete only after testing it on your own environment.

## VM health

- [ ] Kali boots without errors.
- [ ] Terminal launches.
- [ ] System date/time is reasonable.
- [ ] Baseline snapshot is available.

## Network configuration

- [ ] `ip address` output reviewed.
- [ ] `ip route` output reviewed.
- [ ] Expected adapter mode documented.
- [ ] DNS resolver configuration inspected.
- [ ] IP connectivity test attempted if required.
- [ ] DNS lookup tested separately if required.

## Documentation quality

- [ ] Screenshots show the relevant settings clearly.
- [ ] Screenshots do not expose secrets or personal data.
- [ ] Actual results are recorded, including failures.
- [ ] Instructions match the environment used.
- [ ] No unsupported claims of successful testing are included.
